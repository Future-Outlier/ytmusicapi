Package tests
============================================
Tests use the ``unittest`` framework. Each function has a corresponding unittest.
Sometimes there is a single unittest for multiple functions to ensure there are no permanent changes in the user's
YouTube account (i.e. subscribe and unsubscribe).

Note that there must be a ``browser.json`` and ``oauth.json`` in the `tests` folder to run all authenticated tests.
These two files can be easily obtained as the default outputs of running the following commands respectively:

.. code-block:: bash

    ytmusicapi browser
    ytmusicapi oauth



Copy ``tests/test.cfg.example`` to ``tests/test.cfg`` to run the tests. The entry descriptions should be self-explanatory.
For the headers_raw, you need to indent the overflowing lines with a tab character. For the upload test you need a suitable music file in the test directory.
Adjust the file to contain appropriate information for your YouTube account and local setup.

Brand accounts can be created by first signing into the google account you wish to have as the parent/controlling
account then navigating `here. <https://www.youtube.com/create_channel?action_create_new_channel_redirect=true>`_
Once the brand account/channel has been created, you can obtain the account ID needed for your test.cfg by
navigating to your `google account page <https://myaccount.google.com>`_ and selecting the brand account via the
profile drop down in the top right, the brand ID should then be present in the URL.

Coverage badge
--------------
Make sure you installed the dev requirements as explained in `CONTRIBUTING.rst <https://github.com/sigma67/ytmusicapi/blob/master/CONTRIBUTING.rst>`_. Run

.. code-block:: bash

    cd tests
    coverage run -m unittest test.py


to generate a coverage report.