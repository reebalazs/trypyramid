#######################
Pyramid is Easy and Fun
#######################

1. Install Python
-----------------

If you don't have the latest and greatest **Python 3** install it from
`Python.org <https://www.python.org/downloads/>`_

2. Install Pyramid
------------------

Open a terminal::

  $ pyvenv myproject
  $ cd myproject
  $ bin/pip install pyramid

3. Create Your First App
------------------------

Open `app.py` in your editor

.. code-block :: python

  from pyramid.config import Configurator
  from pyramid.response import Response
  from wsgiref.simple_server import make_server

  def hello_world(request):
      return Response('Hello world!')

  def create_app():
      config = Configurator()
      config.add_route('hello_world', '/')
      config.add_view(hello_world, route_name='hello_world')

      app = config.make_wsgi_app()
      return app

  def serve_app():
      app = create_app()
      server = make_server('0.0.0.0', 8080, app)
      server.serve_forever()

  if __name__ == '__main__':
      serve_app()

4. Run Your App
