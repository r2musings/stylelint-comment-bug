This is to show issues in StyleLint with comments.
See:  https://github.com/stylelint/stylelint/issues/7429

Issue is that when there is a comment in the LESS file and `npx stylelint "**/*.less" --fix` is run,
comments from previous lines in the LESS file are lower-cased and space-removed and then pasted
onto a different line in the LESS file causing errors.  It will continue doing this as many times
as you run the command

Before running `npx stylelint "**/*.less" --fix`

```
// Override less variables here
// View all variables: https://github.com/NG-ZORRO/ng-zorro-antd/blob/master/components/style/themes/default.less

@body-background: #121212;
@primary-color: #6200ee;

```

After running `npx stylelint "**/*.less" --fix` twice:

```
// Override less variables here
// View all variables: https://github.com/NG-ZORRO/ng-zorro-antd/blob/master/components/style/themes/default.less

@body-background: #121212;OverridelessvariableshereViewallvariablesOverridelessvariableshereViewallvariables

@primary-color: #6200ee;

```