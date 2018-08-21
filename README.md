# sass-issue-test
Just a personal repo for reproducing certain issues for the [dart-sass](https://github.com/sass/dart-sass) repo.
This issue is related to issue [#451](https://github.com/sass/dart-sass/issues/451)

## Steps to get this bug:
1. Download the repo (obviously)
2. In a terminal or whatever, type in this command: `sass --watch ./main.scss ./main.css --style=compressed --no-source-map` You can also test when not compressed and with a source map, the bug still happens (but not as often?)
3. Then try adding a new scss file and defining a mixin or variable, import it into main.scss and use them in main.scss
4. It will say compiled but in the output, only reads old code.

### Note:
This bug can be sometimes a pain to catch. As I was reproing this bug, I accidentally restarted the compiler and it disappeared. However, I can be definitely sure that the bug lies in the importing of files and using defined variables and whatnot.

Also done this in dart-sass 1.12.0