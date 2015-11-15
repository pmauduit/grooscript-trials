Roughly copy/pasted from the grooscript angular todo sample

```
$ gradle tasks

[...]
Grooscript tasks
----------------
convert - Convert groovy files to javascript.
convertThread - Start a daemon to convert groovy files to javascript if any file changes.
initStaticWeb - Init static web project.
requireJs - Convert a file and dependencies to require.js modules
requireJsThread - Start a daemon to convert require.js modules if any file changes.
spyChanges - Listen changes in files and send notifications.
syncGsLibs - Synchronize grooscript libraries (grooscript.js, grooscript.min.js and grooscript-tools.js) with grooscript plugin version.
templatesJs - Generate templates js file.
templatesThread - Start a daemon to convert groovy templates to javascript if any file changes.
[...]
```

`convert` task is the one interesting here.

Convert is bound to the build task, so gradle build will basically invoke convert as well.

Note: I tried syncGsLibs but it requires that the js files coming along with
grooscript already exist on the js/lib subfolder. Too bad that forced me to
include them in the git repo(I'd have liked that syncGsLibs would overwrite or
recreate them).

