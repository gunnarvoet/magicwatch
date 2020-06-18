# watchmagic

`watchmagic` adds `%%watch` magic to jupyter notebooks that watches a given directory for file changes. Once a file is changed, the cell is re-evaluated.

## License

Copyright 2020 Gunnar Voet

watchmagic is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or any later version.

watchmagic is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with watchmagic.  If not, see <http://www.gnu.org/licenses/>.

## Installation

Clone the package from https://github.com/gunnarvoet/watchmagic. Then install `watchmagic`
by changing into the root directory and running

```shell
python setup.py install
```

or using [pip](https://pypi.org/project/pip/)

```shell
pip install .
```

## Usage

In the notebook run
```python
%load_ext watchmagic
```
Now you can use the magic by simply putting `%%watch` on the first line of the
cell you are working on. This will watch the current directory and its subdirectories for file changes. For example:
```python
%%watch
print('hello world')
```
will watch the current directory and run the print statement on any file changes. Interrupt the kernel to quit watching for file changes.

## Options
Several command line options exist. Run `%%watch?` to display the following help screen:

```
  %watch [-p PATH] [-r] [-nr]
             [--patterns [PATTERNS [PATTERNS ...]]]
             [--ignore [IGNORE_PATTERNS [IGNORE_PATTERNS ...]]]

watch for file changes and re-evaluate current cell.

optional arguments:
  -p PATH, --path PATH  provides the PATH to watch for file changes. If
                        not provided, the current directory will be
                        watched.
  -r, --recursive       include subdirectories recursively when
                        watching for file changes. This is the default
                        behaviour.
  -nr, --non-recursive  do not include subdirectories when watching for
                        file changes.
  --patterns <[PATTERNS [PATTERNS ...]]>
                        look for files with these PATTERNS.
  --ignore <[IGNORE_PATTERNS [IGNORE_PATTERNS ...]]>
                        ignore files containing IGNORE_PATTERNS when
                        watching for file changes.
```
