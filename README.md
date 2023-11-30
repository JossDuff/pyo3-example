# pyo3-example
Dry run of deploying a pyo3 package to test PyPI using maturin



## commands
`pyenv activate pyo3`

for local testing:

    $ maturin develop
    $ python
    >>> import pyo3_example
    >>> pyo3_example.hello_world()
    'Hello World!'

to deploy to test.pypi:

    $ maturin publish -r testpypi

username: `__token__`

password: `<YOUR-TOKEN>`

make sure to include the `pypi-` prefix on your token and that your token doesn't contain any newline chars

using the deployed package:
    
    $ python -m pip install --index-url https://test.pypi.org/simple/ --no-deps hypersync_client_test

    $ python
    >>> import pyo3_example
    >>> pyo3_example.hello_world()