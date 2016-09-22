Python client for Testdroid Cloud APIv2
=======================================

Dependencies
-----

For Linux installation you need Python dev package.

Ubuntu
`sudo apt-get install python-dev`

Command line
-----

Install it with:
`sudo pip install testdroid`

Upgrade it with:
`sudo pip install testdroid --upgrade`

Usage
-----

`testdroid --help`

Environment variables
-----

* `TESTDROID_APIKEY` API key for the authentication
* `TESTDROID_URL` custom backend URL
* `TESTDROID_DISABLE_SSL_VERIFICATION` disable SSL verification for the HTTP requests


Module
-----

You can use this class as a command line utility or import it to your own code.

Example:

```python
>>> from testdroid import Testdroid
>>> testdroid = Testdroid(apikey="1234567890abc", url="http://localhost:9080/testdroid-cloud")
>>> testdroid.get_test_run(1233, 12345)
{u'displayName': u'Test Run 1', u'logZipState': u'BLANK', u'screenshotZipState': u'BLANK', u'projectId': 12340, u'number': 1, u'successRatio': 0.814815, u'createTime': 1393595647000, u'executionRatio': 1.0, u'state': u'FINISHED', u'startedByDisplayName': u'John Doe', u'id': 10} 
```

Testdroid class reads the environment variables automatically, so this would work as well:

```bash
$ export TESTDROID_APIKEY="1234567890abc"
$ export TESTDROID_URL="http://localhost:9080/testdroid-cloud"
```

```python
>>> from testdroid import Testdroid
>>> testdroid = Testdroid()
>>> testdroid.get_test_run(1233, 12345)
{u'displayName': u'Test Run 1', u'logZipState': u'BLANK', u'screenshotZipState': u'BLANK', u'projectId': 12340, u'number': 1, u'successRatio': 0.814815, u'createTime': 1393595647000, u'executionRatio': 1.0, u'state': u'FINISHED', u'startedByDisplayName': u'John Doe', u'id': 10} 
```

Versions
--------

0.1.9 works with Testdroid Cloud 2.4.

From Python API client 2.5 the versions match with Testdroid API versions.

Developing and testing
----------------------

Set up sandbox

`virtualenv myenv && source myenv/bin/activate`

Build example

`python setup.py clean && python setup.py sdist && pip install -U dist/testdroid-0.1.7.tar.gz`

Usage

`testdroid`


Troubleshooting
-----

If you see Pillow error messages on Linux you are most likely missing python-dev, see dependencies.

