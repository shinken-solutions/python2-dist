## Repos avec:
 * python 2.7.18 pour redhat8
   * avec pip/setuptools/wheels
 * Centos7: virtual env pour graphite (/opt/shinken/shinken_venv_graphite_centos7) avec ce qu'il faut pour carbon & apache
 * RedHat8: virtual env pour graphite (/opt/shinken/shinken_venv_graphite_redhat8) avec ce qu'il faut pour carbon & apache* 

# Builder Python sur redhat 8
## Pour le builder:
    tar vftz python-2.7.18-centos8.tar.gz
    ./configure --with-cxx-main=/usr/bin/g++ --prefix=/opt/shinken/python27 LDFLAGS=-Wl,-rpath=/opt/shinken/python27/lib  --enable-optimizations
    make -j4
    make install

### On y rajoute ensuite pip and co

    curl -sSL https://bootstrap.pypa.io/pip/2.7/get-pip.py  -o get-pip.py
    /opt/shinken/python27/bin/python2.7 get-pip.py

Et ensuite on tar le tout