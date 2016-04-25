## Overview ##
![http://djangodev.free.fr/django-graphviz/djangographviz.gif](http://djangodev.free.fr/django-graphviz/djangographviz.gif)

Django data visualization with graphviz.

![http://djangodev.free.fr/django-graphviz/django-graphviz.png](http://djangodev.free.fr/django-graphviz/django-graphviz.png)


The django\_graphviz django project provides 2 applications:
  * _graphviz_: the main component, embeddable in any project
  * _testapp_: a sample application


## Example ##
The models of the testapp application:

![http://djangodev.free.fr/django-graphviz/testapp.dot.png](http://djangodev.free.fr/django-graphviz/testapp.dot.png)

A typical diagram that may be generated:

![http://djangodev.free.fr/django-graphviz/main.dot.png](http://djangodev.free.fr/django-graphviz/main.dot.png)

## How to ? ##

  * add the _graphviz_ application to your django project
  * set the _GRAPHVIZ\_DOT\_CMD_ setting with the absolute path of the 'dot' command
  * add a line like  _(r'^graphviz/', include('graphviz.urls')),_ in the main _urls.py_ file
  * add some methods to your data models; you can find the specifications in the _graphviz/interfaces.py_; the objects that implements those interfaces may be either django models or simple classes; take a look at the sample application, specially the file _testapp/models.py_
  * instantiate a Graph object; you just have to give a "root" object that implements the IGraph interface
  * you may customize the graph by adding some ArrowVisual and NodeVisual instances
  * that's all: you can now download a dot file or an image from the Graph admin page.


## Commands ##
Moreover, the\_graphviz_application provides the_modelviz_command that generates a dot file describing models._

Usage: _python manage.py modelviz app1 '['app2 ...']' > diagram.dot_

The command _python manage.py modelviz graphviz_ generates a UML-like diagram of the _graphviz_ django component:

![http://djangodev.free.fr/django-graphviz/graphviz.dot.png](http://djangodev.free.fr/django-graphviz/graphviz.dot.png)

The command _python manage.py modelviz testapp_ generates a UML-like diagram of the sample _testapp_ application:

![http://djangodev.free.fr/django-graphviz/testapp.dot.png](http://djangodev.free.fr/django-graphviz/testapp.dot.png)