.. title: ModuleNotFoundError: No module named 'flask.ext'
.. slug: modulenotfounderror-no-module-named-flaskext
.. date: 2019-07-15 10:54:21 UTC+08:00
.. tags: Python
.. category: Python
.. link: 
.. description: 
.. type: text


错误信息


.. code-block:: python

   ModuleNotFoundError: No module named 'flask.ext'

把

.. code-block:: python

   from flask.ext.sqlalchemy import SQLAlchemy

改成

.. code-block:: python

   from flask_sqlalchemy import SQLAlchemy

