.. _chap-installing:

Installing ``esig``
===================
Once you have checked out the :ref:`chap-prerequisites`, you're ready to install ``esig``. And it should be really easy!
To install, create a new `virtual environment <https://virtualenv.pypa.io/en/stable/>`_ (if you want to), or activate the one you wish to install it to. Once you're ready to install, run the following command from your terminal or Windows command prompt.

.. code::
	
	$ pip install esig

That should be it. ``esig`` should install, either from a precompiled `wheel <https://wheel.readthedocs.io/en/latest/>`_ for your platform, or build the package from the source. If it builds from source, expect compilation time to take 5-10 minutes depending upon your system. If you already have ``esig`` installed and wish to upgrade to a newer version, run the following command.

.. code::
	
	$ pip install esig --upgrade

Once installed, you can test that the install process worked as expected by trying the following commands.

.. code::
	
	$ python -c "import esig; esig.is_library_loaded()"
	True

If you see ``True``, then all is well, and you're ready to go. If you don't see ``True``, but ``False`` and an error, check out :ref:`chap-troubleshooting`.