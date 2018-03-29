# jupyter-binder-hello-world

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/cs224/jupyter-binder-hello-world/master)

* [Binder documentation](https://mybinder.readthedocs.io/en/latest/)
* [Sample binder repos](https://github.com/jupyterhub/binder/blob/master/doc/sample_repos.md)
* [Anaconda managing environments](https://conda.io/docs/user-guide/tasks/manage-environments.html)

Activate [npstripout](https://github.com/kynan/nbstripout) in your local repository to make sure that you do not commit huge notebooks to the repository:

    pip install --upgrade nbstripout
    nbstripout --install
    nbstripout --install --attributes .gitattributes


Test it locally outside of binder:

    conda env create # conda env create -n jupyter-binder-hello-world
    # conda env update
    # conda remove --name jupyter-binder-hello-world --all
    source activate jupyter-binder-hello-world
    source deactivate
    conda info --envs # or: conda env list
    conda list -n jupyter-binder-hello-world
    conda env export > environment_.yml

Pay attention to `.condarc` for the channels it contains:

    $ cat ~/.condarc
    channels:
      - pyviz
      - conda-forge
      - defaults

Check on the command line if a module is installed:

    python -c "import watermark"

See [notes-on-anaconda](http://vincebuffalo.org/notes/2017/08/28/notes-on-anaconda.html) for some pitfalls, especially around [not being able to specify channels on a per dependency level](https://github.com/conda/conda/issues/2800).
