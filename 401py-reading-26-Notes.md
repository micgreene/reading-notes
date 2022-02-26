# Intro to Django

## Object-relational mapper
+ Deﬁne your data models entirely in Python. You get a rich, dynamic database-access API for free — but you can still write SQL if needed.
+ import re

## URLs and views
+ A clean, elegant URL scheme is an important detail in a high-quality web application. Django encourages beautiful URL design and doesn’t put any cruft in URLs, like .php or .asp.
+ To design URLs for an application, you create a Python module called a URLconf. Like a table of contents for your app, it contains a simple mapping between URL patterns and your views.
+ `from django.urls import path`<br />
`from . import views`<br />
`urlpatterns = [`<br />
     &nbsp;&nbsp;`path('bands/', views.band_listing, name='band-list'),`<br />
     &nbsp;&nbsp;`path('bands/<int:band_id>/', views.band_detail, name='band-detail'),`<br />
     &nbsp;&nbsp;`path('bands/search/', views.band_search, name='band-search'),`<br />
`]`<br /> <br />     
`from django.shortcuts import render`<br />
`def band_listing(request):`<br />
     &nbsp;&nbsp;`"""A view of all bands."""`<br />
     &nbsp;&nbsp;`bands = models.Band.objects.all()`<br />
     &nbsp;&nbsp;`return render(request, 'bands/band_listing.html', {'bands': bands})`<br />

## Templates
+ Django’s template language is designed to strike a balance between power and ease. It’s designed to feel comfortable and easy-to-learn to those used to working with HTML, like designers and front-end developers. But it is also flexible and highly extensible, allowing developers to augment the template language as needed.<br />
`<html>`<br />
  &nbsp;&nbsp;`<head>`<br />
     &nbsp;&nbsp; &nbsp;&nbsp;`<title>Band Listing</title>`<br />
  &nbsp;&nbsp;`</head>`<br />
   &nbsp;&nbsp;`<body>`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;`<h1>All Bands</h1>`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`<ul>`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`{% for band in bands %}`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<li>`<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>`<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`{% if band.can_rock %}<p>This band can rock!</p>{% endif %}`<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`</li>`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`{% endfor %}`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;`</ul>`<br />
   &nbsp;&nbsp;`</body>`<br />
`</html>`<br />

## Forms
+ Django provides a powerful form library that handles rendering forms as HTML, validating user-submitted data, and converting that data to native Python types. Django also provides a way to generate forms from your existing models and use those forms to create and update data.
+ `from django import forms`<br /><br />

`class BandContactForm(forms.Form):`<br />
    &nbsp;&nbsp;`subject = forms.CharField(max_length=100)`<br />
    &nbsp;&nbsp;`message = forms.CharField()`<br />
    &nbsp;&nbsp;`sender = forms.EmailField()`<br />
    &nbsp;&nbsp;`cc_myself = forms.BooleanField(required=False)`<br />

## Authentication
+ Django comes with a full-featured and secure authentication system. It handles user accounts, groups, permissions and cookie-based user sessions. This lets you easily build sites that allow users to create accounts and safely log in/out.
+ `from django.contrib.auth.decorators import login_required`<br />
`from django.shortcuts import render`<br /><br />

`@login_required`<br />
`def my_protected_view(request):`<br />
    &nbsp;&nbsp;`"""A view that can only be accessed by logged-in users"""`<br />
    &nbsp;&nbsp;`return render(request, 'protected.html', {'current_user': request.user})`<br />

## Admin
+ One of the most powerful parts of Django is its automatic admin interface. It reads metadata in your models to provide a powerful and production-ready interface that content producers can immediately use to start managing content on your site. It’s easy to set up and provides many hooks for customization.
+ `from django.contrib import admin`<br />
`from bands.models import Band, Member`<br /><br />

`class MemberAdmin(admin.ModelAdmin):`<br />
    &nbsp;&nbsp;`"""Customize the look of the auto-generated admin for the Member model"""`<br />
    &nbsp;&nbsp;`list_display = ('name', 'instrument')`<br />
    &nbsp;&nbsp;`list_filter = ('band',)`<br /><br />

`admin.site.register(Band)  # Use the default options`<br />
`admin.site.register(Member, MemberAdmin)  # Use the customized options`<br />

## Internationalization
+ Django offers full support for translating text into different languages, plus locale-specific formatting of dates, times, numbers, and time zones. It lets developers and template authors specify which parts of their apps should be translated or formatted for local languages and cultures, and it uses these hooks to localize web applications for particular users according to their preferences.

## Security
+ Django provides multiple protections against:
  + Clickjacking
  + Cross-site scripting
  + Cross Site Request Forgery (CSRF)
  + SQL injection
  + Remote code execution
