# Django CRUD and Forms

## HTML Forms
+ The form is defined in HTML as a collection of elements inside <form>...</form> tags, containing at least one input element of type="submit".
+ The submit input will be displayed as a button (by default) that can be pressed by the user to upload the data in all the other input elements in the form to the server (in this case, just the team_name). 
+ The form attributes define the HTTP method used to send the data and the destination of the data on the server (action):
  + action: The resource/URL where data is to be sent for processing when the form is submitted. If this is not set (or set to an empty string), then the form will be submitted back to the current page URL.
  + method: The HTTP method used to send the data: post or get.
    + The POST method should always be used if the data is going to result in a change to the server's database because this can be made more resistant to cross-site forgery request attacks.
    + The GET method should only be used for forms that don't change user data (e.g. a search form). It is recommended for when you want to be able to bookmark or share the URL.

## Django form handling process
+ Based on the diagram above, the main things that Django's form handling does are:
  + Display the default form the first time it is requested by the user.
    + The form may contain blank fields (e.g. if you're creating a new record), or it may be pre-populated with initial values (e.g. if you are changing a record, or have useful default initial values).
    + The form is referred to as unbound at this point, because it isn't associated with any user-entered data (though it may have initial values).
  + Receive data from a submit request and bind it to the form.
    + Binding data to the form means that the user-entered data and any errors are available when we need to redisplay the form.
  + Clean and validate the data.
    + Cleaning the data performs sanitization of the input (e.g. removing invalid characters that might be used to send malicious content to the server) and converts them into consistent Python types.
    + Validation checks that the values are appropriate for the field (e.g. are in the right date range, aren't too short or too long, etc.)
  + If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
  + If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)
  + Once all actions are complete, redirect the user to another page.

## Form
+ Declaring a Form
  + The declaration syntax for a Form is very similar to that for declaring a Model, and shares the same field types (and some similar parameters). This makes sense because in both cases we need to ensure that each field handles the right types of data, is constrained to valid data, and has a description for display/documentation.
  + Form fields
    + There are many form fiel types:
      + BooleanField, CharField, ChoiceField, TypedChoiceField, DateField, DateTimeField, DecimalField, DurationField, EmailField, FileField, FilePathField, FloatField, ImageField, IntegerField, GenericIPAddressField, MultipleChoiceField, TypedMultipleChoiceField, NullBooleanField, RegexField, SlugField, TimeField, URLField, UUIDField, ComboField, MultiValueField, SplitDateTimeField, ModelMultipleChoiceField, ModelChoiceField.
    + The arguments that are common to most fields:
      + required: If True, the field may not be left blank or given a None value. Fields are required by default, so you would set required=False to allow blank values in the form.
      + rlabel: The label to use when rendering the field in HTML. If a label is not specified, Django will create one from the field name by capitalizing the first letter and replacing underscores with spaces (e.g. Renewal date).
      + rlabel_suffix: By default, a colon is displayed after the label (e.g. Renewal date​:). This argument allows you to specify a different suffix containing other character(s).
      + rinitial: The initial value for the field when the form is displayed.
      + rwidget: The display widget to use.
      + rhelp_text (as seen in the example above): Additional text that can be displayed in forms to explain how to use the field.
      + rerror_messages: A list of error messages for the field. You can override these with your own messages if needed.
      + rvalidators: A list of functions that will be called on the field when it is validated.
      + rlocalize: Enables the localization of form data input (see link for more information).
      + rdisabled: The field is displayed but its value cannot be edited if this is True. The default is False.
