# Configuring Django Settings: Best Practices

## Managing Django Settings: Issues

### Different environments 

+ Usually, you have several environments: local, dev, ci, qa, staging, production, etc. 
+ Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). 
+ You need an approach that allows you to keep all these Django setting configurations.

### Sensitive data

+ You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. 
+ This data cannot be stored in VCS.

### Sharing settings between team members

+ You need a general approach to eliminate human error when working with the settings. For example, a developer may add a third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.

### Django settings are a Python code

+ This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

## Setting Configuration: Different Approaches

+ There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best. Let’s take a brief look at the most popular ones to examine their weaknesses and strengths.

`settings_local.py`
+ his is the oldest method.
+ The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS. Here’s an example:

+ settings.py file:

`ALLOWED_HOSTS = ['example.com']`<br />
`DEBUG = False`<br />
`DATABASES = {`<br />
    `'default': {`<br />
        `'ENGINE': 'django.db.backends.postgresql',`<br />
        `'NAME': 'production_db',`<br />
        `'USER': 'user',`<br />
        `'PASSWORD': 'password',`<br />
        `'HOST': 'db.example.com',`<br />
        `'PORT': '5432',`<br />
        `'OPTIONS': {`<br />
            `'sslmode': 'require'`<br />
        `}`<br />
    `}`<br />
`}`<br />

+ settings_local.py file:

`ALLOWED_HOSTS = ['localhost']`<br />
`DEBUG = True`<br />
`DATABASES = {`<br />
    `'default': {`<br />
        `'ENGINE': 'django.db.backends.postgresql',`<br />
        `'NAME': 'local_db',`<br />
        `'HOST': '127.0.0.1',`<br />
        `'PORT': '5432',`<br />
    `}`<br />
`}`<br />
<br />
+ **Pros:**
  + Secrets not in VCS.
+ **Cons:**
  + settings_local.py is not in VCS, so you can lose some of your Django environment settings.
  + The Django settings file is a Python code, so settings_local.py can have some non-obvious logic.
  + You need to have settings_local.example (in VCS) to share the default configurations for developers.

### Separate settings file for each environment
+ This is an extension of the previous approach. It allows you to keep all configurations in VCS and to share default settings between developers.

+ In this case, you make a settings package with the following file structure:

settings/<br />
   ├── __init__.py<br />
   ├── base.py<br />
   ├── ci.py<br />
   ├── local.py<br />
   ├── staging.py<br />
   ├── production.py<br />
   └── qa.py<br />
   <br />
**settings/local.py:**

`ALLOWED_HOSTS = ['localhost']`<br />
`DEBUG = True`<br />
`DATABASES = {`<br />
    `'default': {`<br />
        `'ENGINE': 'django.db.backends.postgresql',`<br />
        `'NAME': 'local_db',`<br />
        `'HOST': '127.0.0.1',`<br />
        `'PORT': '5432',`<br />
    `}`<br />
`}`<br />
<br />

+ **Pros:**
  + All environments are in VCS.
  + It’s easy to share settings between developers.
+ **Cons:**
  + You need to find a way to handle secret passwords and tokens.
  + “Inheritance” of settings can be hard to trace and maintain.
  + 
### Environment variables

+ To solve the issue with sensitive data, you can use environment variables.
<br />
`SECRET_KEY = os.environ['SECRET_KEY']`<br />
`DATABASES = {`<br />
    `'default': {`<br />
        `'ENGINE': 'django.db.backends.postgresql',`<br />
        `'NAME': os.environ['DATABASE_NAME'],`<br />
        `'HOST': os.environ['DATABASE_HOST'],`<br />
        `'PORT': int(os.environ['DATABASE_PORT']),`<br />
    `}`<br />
`}`<br />
<br />
+ This is the simplest example using Python os.environ and it has several issues:
  + You need to handle KeyError exceptions.
  + You need to convert types manually (see DATABASE_PORT usage).
 
+ To fix KeyError, you can write your own custom wrapper. For example:

`from django.core.exceptions import ImproperlyConfigured`<br />
<br />
`def get_env_value(env_variable):`<br />
    `try:`<br />
      	`return os.environ[env_variable]`<br />
    `except KeyError:`<br />
        `error_msg = 'Set the {} environment variable'.format(var_name)`<br />
        `raise ImproperlyConfigured(error_msg)`<br />
`SECRET_KEY = get_env_value('SECRET_KEY')`<br />
`DATABASES = {`<br />
    `'default': {`<br />
        `'ENGINE': 'django.db.backends.postgresql',`<br />
        `'NAME': get_env_value('DATABASE_NAME'),`<br />
        `'HOST': get_env_value('DATABASE_HOST'),`<br />
        `'PORT': int(get_env_value('DATABASE_PORT')),`<br />
    `}`<br />
`}`<br />
<br />
+ Also, you can set default values for this wrapper and add type conversion. But actually there is no need to write this wrapper, because you can use a third-party library.

+ **Pros:**
  + Configuration is separated from code.
  + Environment parity – you have the same code for all environments.
  + No inheritance in settings, and cleaner and more consistent code.
  + There is a theoretical grounding for using environment variables – 12 Factors.
+ **Cons:**
  + You need to handle sharing default config between developers.
 
### 12 Factors

+ 12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.

+ As the name suggests, the collection consists of twelve parts: 
  + Codebase
  + Dependencies
  + Config
  + Backing services
  + Build, release, run
  + Processes
  + Port binding
  + Concurrency
  + Disposability
  + Dev/prod parity
  + Logs
  + Admin processes
  
+ Each point describes a recommended way to implement a specific aspect of the project. 
+ Some of these points are covered by instruments like Django, Python, pip. Some are covered by design patterns or the infrastructure setup. 

+ Its main rule is to store configuration in the environment. Following this recommendation will give us strict separation of config from code.

## Naming Conventions

+ Give meaningful names to your settings.
+ Always use the prefix with the project name for your custom (project) settings.
+ Write descriptions for your settings in comments.
