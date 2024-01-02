This is to show issues in StyleLint with comments.
See:  https://github.com/stylelint/stylelint/issues/7429

Issue is that when there is a comment in the LESS file and `npx stylelint "**/*.less" --fix` is run,
comments from previous lines in the LESS file are lower-cased and space-removed and then pasted
onto a different line in the LESS file causing errors.
