# Django signals

Django signals are a way to allow decoupled applications to get notified when 
certain actions or events occur within a Django project. Signals provide a 
mechanism for sending and receiving notifications between different parts of 
an application, allowing for loosely coupled communication. 

Django signals are implemented using the Observer pattern, where senders 
generate signals, and receivers handle those signals. The senders and 
receivers are completely decoupled and unaware of each other, which promotes 
modularity and extensibility in your codebase. 

Here's an example to illustrate how Django signals work: 

Let's say we have a Django application for a blog, and we want to send a 
notification whenever a new comment is posted on a blog post. We can use 
signals to achieve this. First, we need to define the signal and its sender. 

```python
# signals.py

from django.dispatch import Signal

new_comment_added = Signal(providing_args=["comment"])
```

In this example, we define a signal named `new_comment_added`. The `
providing_args` argument is used to specify the arguments that will be passed 
along with the signal when it is sent. 

Next, we need to define a receiver function that will be triggered when the 
signal is sent. 

```python
# receivers.py

from django.dispatch import receiver
from django.core.mail import send_mail
from .signals import new_comment_added

@receiver(new_comment_added)
def send_notification(sender, comment, **kwargs):
    subject = "New Comment Posted"
    message = f"A new comment has been posted on the blog: {comment}"
    send_mail(subject, message, "admin@example.com", ["admin@example.com"])
```

In this example, we import the `receiver` decorator and the `
new_comment_added` signal. We then define a function called `
send_notification`, which will be executed when the `new_comment_added` 
signal is sent. The function takes the sender, comment, and any additional 
keyword arguments provided with the signal. 

In our case, when a comment is created, we can send the signal by calling 
the `send()` method on the signal. 

```python
# views.py

from django.shortcuts import render
from .models import Comment
from .signals import new_comment_added

def add_comment(request):
    # Code to create a new comment
    comment = Comment.objects.create(...)
    new_comment_added.send(sender=Comment, comment=comment)
    return render(request, "add_comment.html")
```

In this example, when a new comment is created, we send the `
new_comment_added` signal and pass the sender as `Comment` (the model class) 
and the comment itself. 

When the signal is sent, the `send_notification` function in the receiver is 
triggered. In this case, the function sends an email notification to the 
admin. 

This is just a simple example to illustrate the concept of Django signals. 
They can be used in various scenarios to achieve different functionalities in 
your Django application. 

