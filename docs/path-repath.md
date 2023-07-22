# path or re-path

## With Django which should I use: path or re_path?

In Django, both `path` and `re_path` are used for defining URL patterns in 
your application's URL configuration. However, they have some differences in 
how they match and handle URLs. 

1. `path`: The `path` function is a simplified version of URL pattern 
matching and is recommended for most cases. It uses simple string matching to 
match the requested URL against the specified pattern. You can use 
placeholders (`<str>`, `<int>`, etc.) to capture different types of URL 
parameters. For example:

   ```python
   from django.urls import path
   
   urlpatterns = [
       path('example/<int:id>/', views.example_view),
   ]
   ```

   The `path` function is more readable and expressive for most URL patterns.

2. `re_path`: The `re_path` function allows you to use regular expressions to 
define more complex URL patterns. It provides more flexibility compared to `
path`. If you have advanced matching requirements or need to use regular 
expressions, `re_path` is the appropriate choice. Here's an example:

   ```python
   from django.urls import re_path
   
   urlpatterns = [
       re_path(r'^example/(?P<id>\d+)/$', views.example_view),
   ]
   ```

   The `re_path` function uses regular expression patterns (prefixed with `r`) 
   to match the requested URL.


In general, if your URL patterns can be expressed using simple string 
matching and placeholders, `path` is recommended for its simplicity and 
readability. If you need more complex matching using regular expressions, you 
can use `re_path`. 


