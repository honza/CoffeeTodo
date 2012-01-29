Part 2
======

In this part of the tutorial, we will create a basic structure for our project.

Create a directory for your project called ``todo/``. In it, create a file
called ``index.html``. This will be our only html file. Open it and add a basic
html document structure.

Create the following directory structure inside of ``todo/``:

::

    todo/
        lib/
            jquery.js
            underscore.js
            backbone.js
        src/
            apps/
            collections/
            models/
            utils/
            views/
        css/
            style.css
        index.html

Now, download the following three files into the ``lib/`` directory and add
them to the head of the document:

* `jQuery`_
* `Underscore.js`_
* `Backbone.js`_


Compilation
-----------

In order to compile your CoffeeScript files to JavaScript, you will use the
``coffee`` utility. To compile a ``test.coffee`` to ``test.js``, you run:

::

    $ coffee -c test.coffee

This works on a whole directory, too:

::

    $ coffee -c src/

If you don't want to be compiling your files by hand each time you make a
change, you can use the built-in file watcher.

::

    $ coffee -wc src/*.coffee

This will watch all CoffeeScript files in the ``src/`` directory and compile
them to JavaScript when changes are made.

Go ahead and try that now. Write some random CoffeeScript and see what it
compiles to.


.. _jQuery: http://jquery.com
.. _Underscore.js: http://documentcloud.github.com/underscore/
.. _Backbone.js: http://documentcloud.github.com/backbone/
