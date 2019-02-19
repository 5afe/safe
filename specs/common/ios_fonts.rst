===========================
iOS Fonts
===========================

According to the iOS `Visual Design Human Interface Guidelines for Typography`_, the fonts used in design mockups should be of correct typeface and tracking (letter spacing).

Particularly, for font sizes of 20 points and above, interface mockups should use ``SF Pro Display`` with correct tracking, and for font sizes of 19 points and smaller, interface mockups should use ``SF Pro Text`` typeface with appropriate tracking.

The tracking tables for different point sizes are given in the guidelines referenced above, but they specify tracking in 1/1000em units, which translates to ``fontSizeInPoints / 1000`` multiplier for the specified tracking values.

For example, for the font size of 20 (points) and tracking of +19 (1/1000 em), the tracking in points is ``19 * 20 / 1000 = 0,38``. 

You can find and download all of the values precalculated for you in the tables in `iOS Font Usage`_ document.


.. _`Visual Design Human Interface Guidelines for Typography`: https://developer.apple.com/design/human-interface-guidelines/ios/visual-design/typography/
.. _`iOS Font Usage`: iOS_font_usage.pdf
