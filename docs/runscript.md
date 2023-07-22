# runscript (Django-Extensions)

Which command would be equivalent to `python manage.py shell` but instead of 
running the shell would run a script?

To run a script instead of the Django shell using the `python manage.py 
shell` command, you can use the `runscript` command provided by the Django-
Extensions package. Here's how you can do it: 


1. Install Django-Extensions if you haven't already:
   ```
   pip install django-extensions
   ```

2. Add `'django_extensions'` to the `INSTALLED_APPS` list in your Django project's 
   `settings.py` file:

   ```python
   INSTALLED_APPS = [
       # other apps
       'django_extensions',
   ]
   ```

3. Create a Python script in your Django project's directory (e.g., `scripts/myscript.py`)
   with the code you want to execute. 

4. Create the file

    ```python
    # scripts/myscript.py

    def run():
        # Your code here
        print("Hello from myscript!")
    ```

5. Run the script using the `runscript` command:

   ```
   python manage.py runscript myscript
   ```

Replace `myscript` with the actual name of your script file without the `.py` 
extension. This command will execute the code in the script and provide 
access to your Django project's models, just like the Django shell. 

Make sure you have your Django project set up properly and the necessary 
dependencies installed for your script to run successfully. 
