![Django-Console](https://raw.githubusercontent.com/atmb4u/django-console/master/django-console/static/images/console-128x128.png) 
#Django-Console

bash console in the browser for django devops!

##IMPORTANT

Service needs to be running on ```https``` to securely POST commands to the server. 

![Django-Console](https://raw.githubusercontent.com/atmb4u/django-console/master/django-console/static/images/screenshot.png)

Did a quick update on the code; need to pull the code and restart the server, and waiting for server admin to do that? 
Django-Console is for you!

## Installation

**Step 1**
> pip install django-console

**Step 2**

include __django-console__ into INSTALLED_APPS ```settings.py```

```python
INSTALLED_APPS = (
    # add to the existing apps
    'django-console'
)
```

**Step 3**

include two more variables to ```settings.py```

> Even without these settings, it will work.

> allows requests from all ips, and works even when not in https **(NOT GOOD).**

```python
SECURE_CONSOLE = True  # False to allow http
CONSOLE_WHITELIST = [
                "127.0.0.1"
]  # List of IPs to be allowed - NB: All allowed by default
```
**Step 4**

run
> python manage.py collectstatic

Done!

in your browser, goto http://127.0.0.1:8000/admin/console/ to access the web console.

NB: make sure you got superuser privileges.


##Tip
To run sudo tasks, you can use

```bash
echo mypassword | sudo -S command
```

Example commands 
```bash
$ echo pa$$w0rD | sudo -S service nginx restart

$ git pull origin master

$ ls -al
```

##Caveats

> all the **django superusers** can access this portal, so make sure only the right guys have got access before deploying django-console to live.

> long running tasks and interactive commands won't probably work.


## License

BSD License - checkout LICENSE file for the complete license document


## Author
[Anoop Thomas Mathew](https://twitter.com/atmb4u "atmb4u")
