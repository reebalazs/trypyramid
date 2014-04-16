#######################
Pyramid is Easy and Fun
#######################

Pyramid is super easy to setup and use. Let's do a minimal app using Python 3.

Install Python
--------------

If you don't have the latest and greatest **Python 3** install it from
`Python.org <https://www.python.org/downloads/>`_


Install Pyramid
---------------

Open a terminal::

  pyvenv myproject
  cd myproject
  bin/pip install pyramid waitress


Create Your First App
---------------------

Open `app.py` in your editor

.. code-block :: python

  from pyramid.config import Configurator
  from pyramid.response import Response
  from waitress import serve

  def hello_world(request):
      return Response('Hello world!')

  def create_app():
      config = Configurator()
      config.add_route('hello_world', '/')
      config.add_view(hello_world, route_name='hello_world')

      app = config.make_wsgi_app()
      return app

  if __name__ == '__main__':
      app = create_app()
      serve(app)


Run Your App
------------

.. code-block:: bash

  bin/python app.py


Open The App in a Browser
-------------------------

http://0.0.0.0:8080
