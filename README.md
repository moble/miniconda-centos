This container is similar to
the [official miniconda container](https://hub.docker.com/r/continuumio/miniconda/), but is based on
centos6 so that we can use the same commands as in the (centos-based) manylinux1 container, while
also supporting conda builds on the oldest platform conda supports (centos6).

Note that the official miniconda container uses `tini` as the entrypoint.  I believe this is
because
[jupyter needs a PID reaper](http://jupyter-notebook.readthedocs.io/en/stable/public_server.html#docker-cmd).
I do not intend to run jupyter on this container, so I don't use it.  However, it could be added by
basing off of `krallin/centos-tini:6` instead of `centos:6`.
