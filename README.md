# !!! Remove this section !!!
1. Create empty Git repository with your preferred name: example `django-my-new-pkg-name`
2. Checkout local copy of this new **empty** repository
3. Copy all the contents of this repository inside the **new cloned empty repository**
4. Delete the directory **src\django_pkg.egg-info**
5. Rename the directory inside **src** from `PACKAGE_NAME` to `my_new_pkg_src_location`
6. Massive **replace** with match case the string `model_mixin` with your src location `my_new_pkg_src_location`
7. Massive **replace** the string `django-pkg` with your new package's name `django-my-new-pkg-name`
8. **Edit** the `tests/settings.py` file for the needed configuration to test your app
9. **Rename and edit** the `tests/test_fake.py` file for the needed application's tests
10. Copy or create all source's files of the app inside the **src/my_new_pkg_src_location**
11. Install python's requirements `pip install -r requirements/dev.in`
12. Install python's requirements `pip install -r requirements/requirements.in`
13. Install python's package `pip install .` to test the package's local version
14. Execute `python runtests.py` and validate all tests are passed (if any error is present, the automatic workflow on tag will fail)
15. Edit docs ...
16. Install python requirements `pip install -r requirements/docs.in`
17. Execute `python setup.py sdist bdist_wheel` to build the project
18. Execute `twine upload dist/*` to upload the built files
19. Inside PyPi repository, **generate** new API key with the only scope of project
20. Inside Git repository's settings, section *General*, **enable** the `Allow auto-merge` and `Automatically delete head branches`
21. Inside Git repository's settings, section *Access*, **add access** to be able to execute workflows (as team member's or bot-user collaborator)
22. Inside Git repository's settings, section *Security*, **add security repository secret** named `PYPI_API_TOKEN` to be able to upload packages inside PyPi's repository
23. Add git files as first commit `git add .github .gitattributes .gitignore`

# django-model-mixin [![PyPi license](https://img.shields.io/pypi/l/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)

[![PyPi status](https://img.shields.io/pypi/status/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)
[![PyPi version](https://img.shields.io/pypi/v/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)
[![PyPi python version](https://img.shields.io/pypi/pyversions/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)
[![PyPi downloads](https://img.shields.io/pypi/dm/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)
[![PyPi downloads](https://img.shields.io/pypi/dw/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)
[![PyPi downloads](https://img.shields.io/pypi/dd/django-model-mixin.svg)](https://pypi.python.org/pypi/django-model-mixin)

## GitHub ![GitHub release](https://img.shields.io/github/tag/DLRSP/django-model-mixin.svg) ![GitHub release](https://img.shields.io/github/release/DLRSP/django-model-mixin.svg)

## Test [![codecov.io](https://codecov.io/github/DLRSP/django-model-mixin/coverage.svg?branch=main)](https://codecov.io/github/DLRSP/django-model-mixin?branch=main) [![pre-commit.ci status](https://results.pre-commit.ci/badge/github/DLRSP/django-model-mixin/main.svg)](https://results.pre-commit.ci/latest/github/DLRSP/django-model-mixin/main) [![gitthub.com](https://github.com/DLRSP/django-model-mixin/actions/workflows/ci.yaml/badge.svg)](https://github.com/DLRSP/django-model-mixin/actions/workflows/ci.yaml)

## Check Demo Project
* Check the demo repo on [GitHub](https://github.com/DLRSP/example/tree/django-model-mixin)

## Requirements
-   Python 3.8+ supported.
-   Django 3.2+ supported.

## Setup
1. Install from **pip**:
```shell
pip install django-model-mixin
```

2. Modify `settings.py` by adding the app to `INSTALLED_APPS`:
```python
INSTALLED_APPS = [
    # ...
    "model_mixin",
    # ...
]
```

3. Finally, modify your project `urls.py` with handlers for all errors:
```python
# ...other imports...

urlpatterns = [
    # ...other urls...
]
```

4. Execute Django's command `migrate` inside your project's root:
```shell
python manage.py migrate
Running migrations:
  Applying model_mixin.0001_initial... OK
```

## Run Example Project

```shell
git clone --depth=50 --branch=django-model-mixin https://github.com/DLRSP/example.git DLRSP/example
cd DLRSP/example
python manage.py runserver
```

Now browser the app @ http://127.0.0.1:8000
