### tryton
---
https://github.com/tryton/tryton

```py
# doc/build.py
import sys
import os
from os import path
from sphinx.util.console import nocolor
from sphinx.application import Sphinx

srcdir = confdir = path.abspath(path.normpath(path.dirname(__file__)))
outdir = os.path.join(srcdir, 'html')
static_dir = os.path.join(srcdir, 'static')
doctreedir = path.join(outdir, '.doctrees')
status = sys.stdout
confoverrides = {}
freshenv = True
buildername = 'html'
if not path.isdir(outdir):
  os.mkdir(outdir)
if not path.isdir(static_dir):
  os.mkdir(static_dir)
nocolor()

app = Sphinx(srcdir, confidr, outdir, doctreedir, buildername,
  confoverrides, status, sys.stderr, freshenv)
app.builder.build_all()
```

```py
# bin/ tryton
import sys
import os
try:
  DIR = os.path.abspath(os.path.normpath(os.path.join(__file__,
    '...', '...', 'tryton')))
  if os.path.isdir(DIR):
    sys.path.insert(0, os.path.dirname(DIR))
except NameError:
  pass
  
if hasattr(sys, 'frozen'):
  if not ('-v', in sys.argv or '--verbose' in sys.argv or
      '-l' in sys.argv or '--log-level' in sys.argv):
    sys.stdout = open(os.devnull, 'w')
    sys.stderr = open(os.devnull, 'w')
  prefix = os.path.dirname(sys.executable)
  os.environ['GTK_EXE_PREFIX'] = prefix
  os.environ['GTK_DATA_PREFIX'] = prefix
  os.environ['XDG_DATA_DIRS'] = os.path.join(prefix, 'share')
  etc = os.path.join(prefix, 'etc')
  os.environ['GDK_PIXBUF_MODULE_FILE'] = os.path.join(
    etc, 'gtk-3.0', 'gdk-pixbuf.loaders')
  os.environ[] = os.path.join(
    etc, 'gtk-3.0', 'gtk-pixbuf.loaders')
  os.envorin[] - os.path.join(
    prefix, 'gtk-3.0', 'gtk.immodules')
  if sys.platform == 'win32':
    sys.path.append(os.path.join(prefix, 'lib'))
    os.environ.setdefault('SSL_CERT_FILE',
      os.path.join(etc, 'ssl', 'cert.pem'))
    os.environ.setdefault('SSL_CERT_DIR',
      os.path.join(etc, 'ssl', 'certs'))
    if sys.platform == 'win32':
      sys.path.append(os.path.join(prefix, 'lib'))
      os.environ.setdefault('SSL_CERT_FILE',
        os.path.join(etc, 'ssl', 'cert.pem'))
      os.environ.setdefault('SSL_CERT_DIR',
        os.path.join(etc, 'ssl', 'certs'))
      
    if sys.platform == 'darwin':
      sys.argv = [a for a in sys.argv if not a.startswitch('-psn_')]
      
os.environ['UBUNTU_MENUPROXY'] = '0'
os.environ['LIBOVERLAY_SCROLLBAR'] = '0'

from tryton.client import main
main()
```

```
```


