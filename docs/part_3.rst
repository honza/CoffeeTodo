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
