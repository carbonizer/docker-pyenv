# docker-pyenv

## Purpose

A lighter weight python base, with a non-root user and
[pyenv](https://github.com/yyuu/pyenv) for handling virtualenvs.

## Details

The main python image has both versions of python (at least 3.5.x includes
2.7.x, I haven't checked the 2.7.x image).  There are alternate versions of the
image that a stripped down, but I haven't messed around with those yet.

`pyenv` simplifies building your own version of python.  With the
[`pyenv-virtualenv`](https://github.com/yyuu/pyenv-virtualenv), virtualenvs are
a breeze.  So, two birds, one stone.

I also prefer to run as a non-root user who only has the permissions needed for
the particular task.  The other advantage is that if you want to implement the
same functionality on a real system (perhaps because it doesn't support docker,
for example the beaglebone), it is easier to port the process if it is not
root-centric.

## Shell Initialization Pre-Configured

The shell resource files for bash and zsh (zsh isn't installed, but this is in
preparation for descendent images) are already populate with the `pyenv`
initialization commands.
