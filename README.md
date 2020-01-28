# PythonCodingStandards
Python coding standards for the Bioinformatics Core and HPC team at the
University Health Network


## Introduction
The Bioinformatics Core team utilizes Python as a key programming languages for
the development of pipelines, tools and web applications.  This document
attempts to list standards to ensure consistent Python development among the
team.  The standards will include common Python Developer Guide recommendations
from the core Python developers group and UHN specific standards.


## Python verion
Use Python 3 where possible.  As of January 1, 2020 support for Python 2 has
reached end of life.  Where modules/frameworks/packages require Python 2,
exceptions will be granted for development under this version until updates
are available.


## PEP-8
PEP-8 is the style guide for Python code and provides conventions used in the
standard library.  The guide can be found [here](https://www.python.org/dev/peps/pep-0008/).
The document provides key details in naming conventions, comments (see
Docstring section for more details), and class architecture.

To test compliance with PEP-8, use the `flask8` software package to test code.

```
pip install flake8
flake8 path/to/code/
```


## Docstring
`Docstring` should accompany all function, module, and class definitions.  Use
the [PEP-257](https://www.python.org/dev/peps/pep-0257/) for details on using/
creating Docstrings.

Note that `flake8` can test for Docstring usage and compliance.


## Package and modules
Python code should be organized as packages and modules.  This leads to reusable
code and ease of installation on other systems.  To review Python package
construction, a tutorial is provided [here](https://packaging.python.org/tutorials/packaging-projects/).


## Web development
The UHN HPC and BioCore team develop web applications using a number of
frameworks.  The most common one is [Flask](http://flask.palletsprojects.com/en/1.1.x/)
which provides an entire suite of tools for developing a full stack web
application with minimal effort.  `Flask` utilizes a templating engine to
construct the necessary files and allows embedding of Python into HTML.


### UHN web CSS and JS linking
The team has developed and distributes a common CSS theme which should be used
to provide a consistent web application feel.  The stylesheet can be linked
at the head of a HTML page using:
```
<link rel="stylesheet" href="https://pmgenomics.ca/cdn/css/style.css">
```

In addition, custom Javascript code has been created in conjunctions with the
CSS file to provide interactivity and animation.  These files are also
distributed by the team and can be referenced as follows:
```
<script src="https://pmgenomics.ca/cdn/js/main.js"></script>
<script src="https://pmgenomics.ca/cdn/js/tabView.js"></script>
```

The source code for both the CSS and Javascript can be found here:
* <https://gitlab.com/biocore/tobecdn>


## SQL connectivity
The team utilizes several databases to store and fetch data.  This may include:
* MySQL
* SQLite
* PostgreSQL

To connect Python code to a database, use the [`SQLAlchemy`](https://www.sqlalchemy.org) library which
provides an object relation mapper to SQL based databases and provides code
to connect applications using Python syntax instead of SQL.


## noSQL connectivity
`To be completed`


### Web tutorial
A YouTube tutorial from Corey Schafer provides a basic introduction of the
`Flask` framework and connectivity to a database using `SQLAlchemy` and
can be found here:
* <https://www.youtube.com/playlist?list=PL-osiE80TeTs4UjLw5MM6OjgkjFeUxCYH>


# Version control
All code should be managed using [Git](https://git-scm.com) and stored in a
repostory accessible by the team.  Currently the UHN HPC and BioCore team
uses both:
* [Github](https://github.com/bio-core)
* [Gitlab](https://gitlab.com/biocore)

Note that [Travis CI](https://travis-ci.com/) should be used to test code
prior to every checkin into `Github` and the provided CI/CD tool found in
`GitLab`.

For access to the team repositories, please contact <zhibin.lu@uhnresearch.ca> or
<richard.deborja@uhnresearch.ca>.


