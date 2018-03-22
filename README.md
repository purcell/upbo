# upbo
> :curly_loop: Emacs karma integration that support mode line report!
Upbo is the Korean pronunciation of karma.

* [Features](#Features)
* [Installation](#Installation)
* [Getting Started](#Getting Started)

## Features

### Mode line reporting

### And also terminal log view

## Installation

## Getting Started
Upbo recognizes project in the current buffer based on the git root.
You can apply project-specific test settings using the `define-upbo-test` function in your `init.el`
If you have not set up the project, upbo will find the `kama.conf.js` in git root.

Upbo uses `upbo-karma-command` variable as `karma-cli` path. If `upbo-karma-command` is nil, then by default it looks for a karma executable in global, and if it does not find it, it tries to execute in the project using npx.

### define-upbo-test

``` emacs-lisp
(upbo-define-test
  :path "/path/to/your/project/git/root"
  :browsers "ChromeHeadless"
  :conf-file "/path/to/your/karma-conf/karma.conf.js")
```

* `path` is project git root path
* `browsers` uses as karma `--browsers` option, Currently we support one browser for mode line reporting. if you don't have set, Upbo uses the `browsers` option of the karma configuration.
* `conf-file` is karma configuration to use in the project

### Key Bindings

#### In Minor mode

Keybinding           | Description
---------------------|---------------
<kbd>C-c, u, s</kbd> | Execute karma single run.
<kbd>C-c , s s</kbd> | Execute karma with auto watch.
<kbd>C-c, u, r</kbd> | Open project upbo process view, you need to run karma first.

#### In upbo view mode

Keybinding           | Description
---------------------|---------------
<kbd>s</kbd>         | Execute karma single run.
<kbd>w</kbd>         | Execute karma with auto watch.
<kbd>k</kbd>         | Kill upbo process of current project.
<kbd>q</kbd>         | Close upbo view.



