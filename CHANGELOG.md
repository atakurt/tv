0.0.14 (2021-09-29)
==================

* **Feature 1** Add package to snapcraft to increase accessibility.
* [BUG #55](https://github.com/alexhallam/tv/issues/55):
Fix panic on Unicode string truncation
* [BUG #40](https://github.com/alexhallam/tv/issues/30):
Remove trailing comma.
* [BUG #48](https://github.com/alexhallam/tv/issues/48):
Logicals 1/0 were mentioned in comments, but not implemented.
* [BUG #60](https://github.com/alexhallam/tv/issues/60):
Ellipsis then space, not space then ellipsis.

The rest of the updates had to do with README updates and spelling errors in code comments.

0.0.13 (2021-09-27)
==================
This version was made possible by the contributions of @Lireer! Thank You!

* [PR #40](https://github.com/alexhallam/tv/pull/40) Allow users to specify the deliminator with the `delimiter` option.
* [PR #42](https://github.com/alexhallam/tv/pull/42) `clippy` warnings and code refactoring. 
* [PR #41](https://github.com/alexhallam/tv/pull/41) change `.len()` to `.chars().count()` to avoid potential column widths if the calue contains code points consisting of multiple bytes.

0.0.12 (2021-09-09)
==================
* [BUG #33](https://github.com/alexhallam/tv/issues/33) Elipses used when NA should replace on unquoted string missingness #33
This problem was caused by all of the columns being width 1. When width is 1 the length of the string "NA" is 2. Since 2 was greater
than 1 NA was converted to elipses. To fix this problem I added a min width of 2 and while I was at it I includeed a new option `lower-column-width`
* [BUG #32](https://github.com/alexhallam/tv/issues/32) Column with integer 1 and 0 returns NaN for 0.
This bug was caused by logging 0s. I added a condition on the sigfig decision tree to fix.
* **Feature 1** `lower-column-width`: `The lower (minimum) width of columns. Must be 2 or larger. Default 2. `
* **Feature 2** `upper-column-width`: `The upper (maxiumum) width of columns. Default 20.`
* **Feature 2** `debug-mode`: `Print object details to make it easier for the maintainer to find and resolve bugs.` This is to save me time in the futre :smile:

0.0.10 (2021-08-05)
==================
* [BUG #29](https://github.com/alexhallam/tv/issues/29) Turns out the column count was correct. `tv` was not printing the last column

0.0.9 (2021-08-05)
==================
Minor Mistakes:

* Added color format to additional footer data.
* [BUG #29](https://github.com/alexhallam/tv/issues/29):
Column count was wrong.
* [BUG #28](https://github.com/alexhallam/tv/issues/28):
Accidental extra info printed from debug.

0.0.8 (2021-08-05)
==================
Feature Enhancement:

* [BUG #23](https://github.com/alexhallam/tv/issues/23):
Simplified the regex for floats.
* [BUG #19](https://github.com/alexhallam/tv/issues/19):
Printing "wide" datasets with more columns than space in the terminal resulted in a poor viewer experience. This fix removes extra columns from the print and mentions them in the footer.
