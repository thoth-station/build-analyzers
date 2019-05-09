# Thoth: Build Analysers

This is a set of analysers that will retrieve information from build logs.

<br>

### Lead by Example:

Consider a log produced by the [pip](https://pypi.org/project/pip/) package installer:

> We can also use [pipenv](https://pypi.org/project/pipenv/), see the [How it works](how-it-works) section

<details>
  <summary> Log file content </summary>
  <pre>
Processing /home/macermak/RedHat/aicoe/lab
Collecting networkx (from thoth-lab==0.0.3)
Collecting requests (from thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/7d/e3/20f3d364d6c8e5d2353c72a67778eb189176f08e873c9900e10c0287b84b/requests-2.21.0-py2.py3-none-any.whl
Collecting pandas (from thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/e6/de/a0d3defd8f338eaf53ef716e40ef6d6c277c35d50e09b586e170169cdf0d/pandas-0.24.1-cp36-cp36m-manylinux1_x86_64.whl
Collecting plotly (from thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/fd/db/003b5cfbc710f4d4982440451185b952269e4080a57ae7e760a2ceb8ce0c/plotly-3.6.1-py2.py3-none-any.whl
Collecting decorator>=4.3.0 (from networkx->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/f1/cd/7c8240007e9716b14679bc217a1baefa4432aa30394f7e2ec40a52b1a708/decorator-4.3.2-py2.py3-none-any.whl
Collecting idna<2.9,>=2.5 (from requests->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/14/2c/cd551d81dbe15200be1cf41cd03869a46fe7226e7450af7a6545bfc474c9/idna-2.8-py2.py3-none-any.whl
Collecting urllib3<1.25,>=1.21.1 (from requests->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/62/00/ee1d7de624db8ba7090d1226aebefab96a2c71cd5cfa7629d6ad3f61b79e/urllib3-1.24.1-py2.py3-none-any.whl
Collecting certifi>=2017.4.17 (from requests->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/9f/e0/accfc1b56b57e9750eba272e24c4dddeac86852c2bebd1236674d7887e8a/certifi-2018.11.29-py2.py3-none-any.whl
Collecting chardet<3.1.0,>=3.0.2 (from requests->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/bc/a9/01ffebfb562e4274b6487b4bb1ddec7ca55ec7510b22e4c51f14098443b8/chardet-3.0.4-py2.py3-none-any.whl
Collecting python-dateutil>=2.5.0 (from pandas->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/41/17/c62faccbfbd163c7f57f3844689e3a78bae1f403648a6afb1d0866d87fbb/python_dateutil-2.8.0-py2.py3-none-any.whl
Collecting pytz>=2011k (from pandas->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/61/28/1d3920e4d1d50b19bc5d24398a7cd85cc7b9a75a490570d5a30c57622d34/pytz-2018.9-py2.py3-none-any.whl
Collecting numpy>=1.12.0 (from pandas->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/f5/bf/4981bcbee43934f0adb8f764a1e70ab0ee5a448f6505bd04a87a2fda2a8b/numpy-1.16.1-cp36-cp36m-manylinux1_x86_64.whl
Collecting six (from plotly->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/73/fb/00a976f728d0d1fecfe898238ce23f502a721c0ac0ecfedb80e0d88c64e9/six-1.12.0-py2.py3-none-any.whl
Collecting retrying>=1.3.3 (from plotly->thoth-lab==0.0.3)
Collecting nbformat>=4.2 (from plotly->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/da/27/9a654d2b6cc1eaa517d1c5a4405166c7f6d72f04f6e7eea41855fe808a46/nbformat-4.4.0-py2.py3-none-any.whl
Collecting traitlets>=4.1 (from nbformat>=4.2->plotly->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/93/d6/abcb22de61d78e2fc3959c964628a5771e47e7cc60d53e9342e21ed6cc9a/traitlets-4.3.2-py2.py3-none-any.whl
Collecting jupyter-core (from nbformat>=4.2->plotly->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/1d/44/065d2d7bae7bebc06f1dd70d23c36da8c50c0f08b4236716743d706762a8/jupyter_core-4.4.0-py2.py3-none-any.whl
Collecting jsonschema!=2.5.0,>=2.4 (from nbformat>=4.2->plotly->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/77/de/47e35a97b2b05c2fadbec67d44cfcdcd09b8086951b331d82de90d2912da/jsonschema-2.6.0-py2.py3-none-any.whl
Collecting ipython-genutils (from nbformat>=4.2->plotly->thoth-lab==0.0.3)
  Using cached https://files.pythonhosted.org/packages/fa/bc/9bd3b5c2b4774d5f33b2d544f1460be9df7df2fe42f352135381c347c69a/ipython_genutils-0.2.0-py2.py3-none-any.whl
Building wheels for collected packages: thoth-lab
  Running setup.py bdist_wheel for thoth-lab: started
  Running setup.py bdist_wheel for thoth-lab: finished with status 'done'
  Stored in directory: /tmp/pip-ephem-wheel-cache-_4menpyv/wheels/c6/6e/7d/ef751ae03b7d549816c6658c7f8065cb889a8de3f0c2b3ca6c
Successfully built thoth-lab
selinon 0.1.0rc9 requires celery>=4, which is not installed.
thoth-analyzer 0.1.0 requires distro, which is not installed.
thoth-storages 0.9.5 requires aiogremlin==3.2.6rc1, which is not installed.
tensorflow-tensorboard 1.5.1 has requirement bleach==1.5.0, but you'll have bleach 2.1.4 which is incompatible.
tensorflow-tensorboard 1.5.1 has requirement html5lib==0.9999999, but you'll have html5lib 1.0.1 which is incompatible.
tensorboard 1.6.0 has requirement bleach==1.5.0, but you'll have bleach 2.1.4 which is incompatible.
tensorboard 1.6.0 has requirement html5lib==0.9999999, but you'll have html5lib 1.0.1 which is incompatible.
notebook 5.7.0 has requirement jupyter-client>=5.2.0, but you'll have jupyter-client 5.1.0 which is incompatible.
notebook 5.7.0 has requirement pyzmq>=17, but you'll have pyzmq 16.0.3 which is incompatible.
kaggle 1.4.7.1 has requirement urllib3<1.23.0,>=1.15, but you'll have urllib3 1.24.1 which is incompatible.
botocore 1.11.3 has requirement urllib3<1.24,>=1.20, but you'll have urllib3 1.24.1 which is incompatible.
awscli 1.14.25 has requirement botocore==1.8.29, but you'll have botocore 1.11.3 which is incompatible.
awscli 1.14.25 has requirement colorama<=0.3.7,>=0.2.5, but you'll have colorama 0.3.9 which is incompatible.
awscli 1.14.25 has requirement PyYAML<=3.12,>=3.10, but you'll have pyyaml 3.13 which is incompatible.
thoth-storages 0.9.5 has requirement yarl<1.2, but you'll have yarl 1.3.0 which is incompatible.
spyder-kernels 0.2.6 has requirement jupyter-client>=5.2.3, but you'll have jupyter-client 5.1.0 which is incompatible.
spyder-kernels 0.2.6 has requirement pyzmq>=17, but you'll have pyzmq 16.0.3 which is incompatible.
rstcheck 2.2 has requirement sphinx<1.5,>=1.3, but you'll have sphinx 1.8.1 which is incompatible.
gremlinpython 3.2.6 has requirement six==1.10.0, but you'll have six 1.12.0 which is incompatible.
gremlinpython 3.2.6 has requirement tornado==4.4.1, but you'll have tornado 4.5.2 which is incompatible.
Installing collected packages: decorator, networkx, idna, urllib3, certifi, chardet, requests, six, python-dateutil, pytz, numpy, pandas, retrying, ipython-genutils, traitlets, jupyter-core, jsonschema, nbformat, plotly, thoth-lab
  Found existing installation: decorator 4.3.2
    Uninstalling decorator-4.3.2:
      Successfully uninstalled decorator-4.3.2
  Found existing installation: networkx 2.2
    Uninstalling networkx-2.2:
      Successfully uninstalled networkx-2.2
  Found existing installation: idna 2.8
    Uninstalling idna-2.8:
      Successfully uninstalled idna-2.8
  Found existing installation: urllib3 1.24.1
    Uninstalling urllib3-1.24.1:
      Successfully uninstalled urllib3-1.24.1
  Found existing installation: certifi 2018.11.29
Cannot uninstall 'certifi'. It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall.
You are using pip version 18.1, however version 19.0.2 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
  </pre>
</details>

In the log file, there is a line 76 which contains the information about the package which broke the installation: `certifi`. We want to extract this information. In the most common case, we want to get a **report** containing the observations about this particular build log.

```python
from thoth.build_analysers.analysis import build_breaker_report

log: str = ...
report: dict = build_breaker_report(log)
```

The result is a dictionary which can further be formatted by the convenient `build_breaker_format_report` function.

```python
from thoth.build_analysers.analysis import build_breaker_format_report

print(build_breaker_format_report(report))
```

And you should see something like this:
```
Build breaker:

    {
        "already_satisfied": null,
        "source": "thoth-lab",
        "target": "certifi",
        "version_installed": null,
        "version_specified": ">=2017.4.17"
    }

Probable reason:

    76: Cannot uninstall 'certifi'. It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall.

Candidates:

    [
        "76: Cannot uninstall 'certifi'. It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall."
    ]

```

<br>

### How it works

The logic is quite simple (and also a bit naive). Really, no rocket science, just a lot of string matching.

##### The intuition

The approach currently handles logs produced by pip and pipenv package installers. For both of them, there is a set of patterns which, if found in a log, potentially indicate an error. These patterns are strings formatted according to the [PEP3101](https://www.python.org/dev/peps/pep-3101/) string formatting syntax and are stored in the [`resources`](/thoth/build_analysers/resources) folder as [pandas DataFrames](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.DataFrame.html).

We evaluate the 'goodness' of a match for each line of the log file with respect to the relevant set of patterns and label them based on the given *thresholds*. Currently, the `ERROR` threshold is set to the score of *>=0.6* on the scale from *0* through *1.0*. Finally, we try to search for package names in the log file to construct a dependency table. We filter the `ERROR`s containing a package name and we've got ourselves a list of *build breakers*.

<br>

### Installation

The package is available on [PyPI](https://pypi.org/project/thoth-build-analysers/):

```bash
pip install thoth-build-analysers
```

And you're good to go :thumbsup:

<br>

---

> Author: Marek Cermak <macermak@redhat.com>, @AICoE - Project Thoth
