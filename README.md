# clean

`clean` your source code and files in a directory (recursively) from tab
characters and trailing spaces.

__Please write clean code.__ You shouldn't have to use this often, and never
for your own code!

__Don't be reckless.__ Some files _should_ have tab characters or trailing
whitespace. Read all of the usage below and _know your project_ before you
go changing anything.

## Usage

Within your working directory (e.g. a project directory):
```sh
clean | sh
```

The default tab width is 4 when the tab characters are replaced. There are
two ways to change this value:
- _local_: `clean` takes a parameter of the width. e.g. `clean 2`
- _global_: Set the `TABWIDTH` environment variable. This can be done
  by adding `export TABWIDTH=2` to `~/.bashrc` or equivalent.

The `clean` command alone produces shell commands to be run.
It is recommend that you run `clean` __before__ `clean | sh`, so you
can assert you won't be running or removing anything unintended (changing
files that shouldn't be changed).

You can use grep to choose only files you _want_ to modify:
```sh
# within a 'models' subdirectory (at any depth)
clean | grep '/models/' | sh
# within the immediate 'models' directory
clean | grep ' ./models/' | sh
# files ending in '.txt'
clean | grep '\.txt ' | sh
```

To reiterate, remember to __check the output before piping to shell__.

## Installation

```sh
git clone https://github.com/lukedmor/clean
sudo cp clean/clean /usr/local/bin/
```
