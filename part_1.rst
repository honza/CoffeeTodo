Part 1
======

Installation
------------

Before we can start any coding, we need to make sure that your development
environment has all the necessary applications installed and configured
properly. I'm going to assume that you are using a recent Mac OSX installation.

First of all, you will need the CoffeeScript interpreter. The interpreter runs
on top of `node.js`_ so you will need that, too. You can install both with
homebrew:

::

    $ brew install node
    $ brew install coffee-script

This will give you two commands: ``node`` and ``coffee``. The ``coffee``
command can be used to compile your CoffeeScript files into javascript. More on
that later.

Language primer
---------------

CoffeeScript is a little language that compiles into JavaScript. Underneath all
those awkward braces and semicolons, JavaScript has always had a gorgeous
object model at its heart. CoffeeScript is an attempt to expose the good parts
of JavaScript in a simple way.

The golden rule of CoffeeScript is: "It's just JavaScript". The code compiles
one-to-one into the equivalent JS, and there is no interpretation at runtime.
You can use any existing JavaScript library seamlessly from CoffeeScript (and
vice-versa). The compiled output is readable and pretty-printed, passes through
JavaScript Lint without warnings, will work in every JavaScript implementation,
and tends to run as fast or faster than the equivalent handwritten JavaScript.

Once you've used CoffeeScript or a while, you will not want to go back to plain
JavaScript.

Variables
~~~~~~~~~

In JavaScript, all user-defined variables need to have the ``var`` keyword in
front of it.

.. sourcecode:: javascript

    var name = 'John Smith';

In CoffeeScript, you can safely omit that.

.. sourcecode:: coffee-script

    name = 'John Smith'

Each variable is automatically scoped to the current closure. This prevents you
from accidentally leaking the variable name into the outer scope.

Semicolons and whitespace
~~~~~~~~~~~~~~~~~~~~~~~~~

Instead of relying on semicolons to indicate the end of a statement,
CoffeeScript uses *significant whitespace*. Much like Python, indentation is
used to mark the body of a function or a for-loop.

.. sourcecode:: coffee-script

    files = ['photo.jpg', 'logo.png']

    for file in files
      console.log file

Functions
~~~~~~~~~

Functions in CoffeeScript are composed of only a name and an arrow:

.. sourcecode:: javascript

    var greet = function() {
      console.log('Good morning');
    };

.. sourcecode:: coffee-script

    greet = ->
      console.log 'Good morning'

And with an argument:

.. sourcecode:: javascript

    var greet = function(name) {
      console.log('Good morning, ' + name);
    };

.. sourcecode:: coffee-script

    greet = (name) ->
      console.log 'Good morning, ' + name

Brackets
~~~~~~~~

In simple situations, you can omit the ``()`` syntax.

.. sourcecode:: javascript

    console.log('hello');
    alert('hello');
    parseInt('1234', 10);

can be written as:

.. sourcecode:: coffee-script

    console.log 'hello'
    alert 'hello'
    parseInt '1234', 10

Objects can also be simplified:

.. sourcecode:: javascript

    var user = {
      first: 'John',
      last: 'Smith',
      age: 28
    };

.. sourcecode:: coffee-script

    user =
      first: 'John'
      last: 'Smith'
      age: 28

Note the absence of commas, too.

.. _node.js: http://nodejs.org
