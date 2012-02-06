Part 3
======

Now that you understand a bit about CoffeeScript and have a basic project
structure in place, we can dive into Backbone.

Next, we will have to create a model to store our tasks in, a collection to
manage those models, a view to present the task to the user and an application
class that will hold all of this together.

Open up ``app.coffee`` and add the following basic scaffolding:

.. sourcecode:: coffee-script

    class Task extends Backbone.Model

    class TaskCollection extends Backbone.Collection
      model: Task

    class TaskView extends Backbone.View

    class CoffeeTodo

You can see that our model, collection and view all inherit from Backbone's MVC
components. Note that at this point, the application will do nothing. All we
have done is subclass some base classes. Add the following to the bottom of
your file to kick things off.


.. sourcecode:: coffee-script

    $ ->
      app = new CoffeeTodo

This will create an instance of our application class when the DOM is ready.
It's good practice to add as little code possible to jQuery's document ready
handler. Your application class should distribute tasks to all other parts of
the application.

Models
------

Backbone models are used to represent data in your application. They are very
easy to write and often don't require any customization. In the scaffolding you
have just created we have a ``Task`` model. A task should probably have a
*text* field and a *finished* field. We don't have to do anything special to
say that we would like those fields, we simply set those values on the model
instance.

.. sourcecode:: coffee-script

    task = new Task
    task.set 'text', 'Wash the dishes'
    task.set 'finished', false

Or you can set multiple fields by passing in an object.

.. sourcecode:: coffee-script

    task = new Task
    task.set 
      text: 'Wash the dishes'
      finished: false

If you already have an object that has the right properties, you can pass it in
to the models constructor:

.. sourcecode:: coffee-script

    task = new Task
      text: 'Wash the dishes'
      finished: false

This is helpful when creating model instances after you have received some JSON
from the server.

Getting values from a model is simple. Just use the ``get()`` method.

.. sourcecode:: coffee-script

    task.get 'text'
    # => 'Wash the dishes'
    task.get 'finished'
    # => false

For our task application, it makes sense for new tasks to be not finished. We
can easily set a default value for the *finished* field. We will also set the
text of the task to be an empty string. Modify the class declaration to read.

.. sourcecode:: coffee-script

    class Task extends Backbone.Model
      defaults:
        finished: false
        text: ''
