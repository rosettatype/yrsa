## Fontbakery report

Fontbakery version: 0.7.33

<details>
<summary><b>[15] Yrsa-LightItalic.ttf</b></summary>
<details>
<summary>💔 <b>ERROR:</b> Show hinting filesize impact.</summary>

* [com.google.fonts/check/hinting_impact](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/hinting_impact)
<pre>--- Rationale ---

This check is merely informative, displaying and useful comparison of filesizes
of hinted versus unhinted font files.


</pre>

* 💔 **ERROR** The condition <FontBakeryCondition:hinting_stats> had an error: OSError: Could not find the libc shared library

</details>
<details>
<summary>💔 <b>ERROR:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---

This check finds which version of ttfautohint was used, by inspecting name
table entries and then finds which version of ttfautohint is currently
installed in the system.


</pre>

* 💔 **ERROR** The check <FontBakeryCheck:com.google.fonts/check/old_ttfautohint> had an error: FailedConditionError: The condition <FontBakeryCondition:hinting_stats> had an error: OSError: Could not find the libc shared library

</details>
<details>
<summary>🔥 <b>FAIL:</b> Check license file has good copyright string.</summary>

* [com.google.fonts/check/license/OFL_copyright](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/license/OFL_copyright)
<pre>--- Rationale ---

An OFL.txt file&#x27;s first line should be the font copyright e.g:
&quot;Copyright 2019 The Montserrat Project Authors
(https://github.com/julietaula/montserrat)&quot;


</pre>

* 🔥 **FAIL** First line in license file does not match expected format: "copyright 2010 yrsa and rasa project authors (info@rosettatype.com)"

</details>
<details>
<summary>🔥 <b>FAIL:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---

A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.

The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.

Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;


Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.

When in doubt, please choose OFL for new font projects.


</pre>

* 🔥 **FAIL** License file LICENSE.txt exists but NameID 13 (LICENSE DESCRIPTION) value on platform 3 (WINDOWS) is not specified for that. Value was: "This Font Software is licensed under the SIL Open Font License, Version 1.1. This license is available with a FAQ at: https://scripts.sil.org/OFL" Must be changed to "Licensed under the Apache License, Version 2.0" [code: wrong]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Copyright notices match canonical pattern in fonts</summary>

* [com.google.fonts/check/font_copyright](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/font_copyright)

* 🔥 **FAIL** Name Table entry: Copyright notices should match a pattern similar to: "Copyright 2019 The Familyname Project Authors (git url)"
But instead we have got:
"Copyright 2010 Yrsa and Rasa Project Authors (info@rosettatype.com)" [code: bad-notice-format]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Check if the vertical metrics of a family are similar to the same family hosted on Google Fonts.</summary>

* [com.google.fonts/check/vertical_metrics_regressions](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vertical_metrics_regressions)
<pre>--- Rationale ---

If the family already exists on Google Fonts, we need to ensure that the
checked family&#x27;s vertical metrics are similar. This check will test the
following schema which was outlined in Fontbakery issue #1162 [1]:

- The family should visually have the same vertical metrics as the Regular
style hosted on Google Fonts.
- If the family on Google Fonts has differing hhea and typo metrics, the family
being checked should use the typo metrics for both the hhea and typo entries.
- If the family on Google Fonts has use typo metrics not enabled and the family
being checked has it enabled, the hhea and typo metrics should use the family
on Google Fonts winAscent and winDescent values.
- If the upms differ, the values must be scaled so the visual appearance is the
same.

[1] https://github.com/googlefonts/fontbakery/issues/1162


</pre>

* 🔥 **FAIL** Yrsa Light Italic: OS/2 sTypoAscender is 971 when it should be 728 [code: bad-typo-ascender]
* 🔥 **FAIL** Yrsa Light Italic: OS/2 sTypoDescender is -423 when it should be -272 [code: bad-typo-descender]
* 🔥 **FAIL** Yrsa Light Italic: hhea Ascender is 971 when it should be 728 [code: bad-hhea-ascender]
* 🔥 **FAIL** Yrsa Light Italic: hhea Descender is -423 when it should be -272 [code: bad-hhea-descender]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 usWinAscent & usWinDescent.</summary>

* [com.google.fonts/check/family/win_ascent_and_descent](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/family/win_ascent_and_descent)
<pre>--- Rationale ---

A font&#x27;s winAscent and winDescent values should be greater than the head
table&#x27;s yMax, abs(yMin) values. If they are less than these values, clipping
can occur on Windows platforms
(https://github.com/RedHatBrand/Overpass/issues/33).

If the font includes tall/deep writing systems such as Arabic or Devanagari,
the winAscent and winDescent can be greater than the yMax and abs(yMin) to
accommodate vowel marks.

When the win Metrics are significantly greater than the upm, the linespacing
can appear too loose. To counteract this, enabling the OS/2 fsSelection bit 7
(Use_Typo_Metrics), will force Windows to use the OS/2 typo values instead.
This means the font developer can control the linespacing with the typo values,
whilst avoiding clipping by setting the win values to values greater than the
yMax and abs(yMin).


</pre>

* 🔥 **FAIL** OS/2.usWinDescent value 423 is too large. It should be less than double the yMin. Current absolute yMin value is 206 [code: descent]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---

Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will
only differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.

However, a quotedbl should have 2 contours, unless the font belongs to a
display family.

This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.


</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: uni1E08	Contours detected: 3	Expected: 2
Glyph name: uni1E09	Contours detected: 3	Expected: 2
Glyph name: uni1E1C	Contours detected: 3	Expected: 2
Glyph name: uni1E1D	Contours detected: 4	Expected: 3
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: uni1E08	Contours detected: 3	Expected: 2
Glyph name: uni1E09	Contours detected: 3	Expected: 2
Glyph name: uni1E1C	Contours detected: 3	Expected: 2
Glyph name: uni1E1D	Contours detected: 4	Expected: 3
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---

All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.

If using GlyphsApp, ligature carets can be set directly on canvas by accessing
the `Glyph -&gt; Set Anchors` menu option or by pressing the `Cmd+U` keyboard
shortcut.

If designing with UFOs, (as of Oct 2020) ligature carets are not yet compiled
by ufo2ft, and therefore will not build via FontMake. See
googlefonts/ufo2ft/issues/329


</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---

Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).


</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + i
	- i + j
	- j + t
	- t + v
	- v + w
	- germandbls + i
	- f.ascender + i
	- f.f + i

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check mark characters are in GDEF mark glyph class)</summary>

* [com.google.fonts/check/gdef_spacing_marks](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_spacing_marks)
<pre>--- Rationale ---

Glyphs in the GDEF mark glyph class should be non-spacing.
Spacing glyphs in the GDEF mark glyph class may have incorrect anchor
positioning that was only intended for building composite glyphs during design.


</pre>

* ⚠ **WARN** The following spacing glyphs may be in the GDEF mark glyph class by mistake:
	 uni02C9 [code: spacing-mark-glyphs]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check mark characters are in GDEF mark glyph class</summary>

* [com.google.fonts/check/gdef_mark_chars](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_mark_chars)
<pre>--- Rationale ---

Mark characters should be in the GDEF mark glyph class.


</pre>

* ⚠ **WARN** The following mark characters could be in the GDEF mark glyph class:
	 U+0335 [code: mark-chars]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check GDEF mark glyph class doesn't have characters that are not marks)</summary>

* [com.google.fonts/check/gdef_non_mark_chars](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_non_mark_chars)
<pre>--- Rationale ---

Glyphs in the GDEF mark glyph class become non-spacing and may be repositioned
if they have mark anchors.
Only combining mark glyphs should be in that class. Any non-mark glyph must not
be in that class, in particular spacing glyphs.


</pre>

* ⚠ **WARN** The following non-mark characters should not be in the GDEF mark glyph class:
	 U+02C9 [code: non-mark-chars]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---

This test looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.

This test is not run for variable fonts, as they may legitimately have colinear
vectors.


</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* R: L<<275.0,253.0>--<274.0,253.0>> -> L<<274.0,253.0>--<182.0,253.0>>
	* Racute: L<<275.0,253.0>--<274.0,253.0>> -> L<<274.0,253.0>--<182.0,253.0>>
	* Rcaron: L<<275.0,253.0>--<274.0,253.0>> -> L<<274.0,253.0>--<182.0,253.0>>
	* arrowboth: L<<140.0,300.0>--<175.0,303.0>> -> L<<175.0,303.0>--<788.0,303.0>>
	* arrowdown: L<<247.0,140.0>--<248.0,177.0>> -> L<<248.0,177.0>--<291.0,526.0>>
	* arrowdown: L<<341.0,526.0>--<298.0,177.0>> -> L<<298.0,177.0>--<290.0,139.0>>
	* arrowleft: L<<140.0,300.0>--<175.0,303.0>> -> L<<175.0,303.0>--<527.0,303.0>>
	* arrowup: L<<234.0,52.0>--<277.0,401.0>> -> L<<277.0,401.0>--<285.0,439.0>>
	* arrowup: L<<328.0,438.0>--<327.0,401.0>> -> L<<327.0,401.0>--<284.0,52.0>>
	* arrowupdown: L<<224.0,-57.0>--<225.0,-20.0>> -> L<<225.0,-20.0>--<300.0,588.0>> and 45 more. [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---

This test heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed
up by manual inspection.


</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* at.case: B<<468.0,162.0>-<468.0,187.0>-<474.0,229.0>>/B<<474.0,229.0>-<449.0,153.0>-<412.5,118.0>> = 10.078382116424827
	* at: B<<457.0,72.0>-<457.0,97.0>-<463.0,139.0>>/B<<463.0,139.0>-<438.0,63.0>-<401.5,28.0>> = 10.078382116424827
	* three.dnom: B<<234.0,198.5>-<213.0,186.0>-<192.0,182.0>>/B<<192.0,182.0>-<225.0,183.0>-<252.0,162.5>> = 9.048593278634225
	* three.numr: B<<263.0,429.5>-<242.0,417.0>-<221.0,413.0>>/B<<221.0,413.0>-<254.0,414.0>-<281.0,393.5>> = 9.048593278634225
	* three.tf: B<<323.5,291.5>-<294.0,273.0>-<263.0,265.0>>/B<<263.0,265.0>-<292.0,267.0>-<319.5,254.5>> = 10.525107871028323
	* threequarters: B<<263.0,429.5>-<242.0,417.0>-<221.0,413.0>>/B<<221.0,413.0>-<254.0,414.0>-<281.0,393.5>> = 9.048593278634225
	* uni00B3: B<<273.0,526.5>-<252.0,514.0>-<231.0,510.0>>/B<<231.0,510.0>-<264.0,511.0>-<291.0,490.5>> = 9.048593278634225 and uni2083: B<<220.0,98.5>-<199.0,86.0>-<178.0,82.0>>/B<<178.0,82.0>-<211.0,83.0>-<238.0,62.5>> = 9.048593278634225 [code: found-jaggy-segments]

</details>
<br>
</details>

### Summary

| 💔 ERROR | 🔥 FAIL | ⚠ WARN | 💤 SKIP | ℹ INFO | 🍞 PASS | 🔎 DEBUG |
|:-----:|:----:|:----:|:----:|:----:|:----:|:----:|
| 2 | 5 | 8 | 91 | 7 | 81 | 0 |
| 1% | 3% | 4% | 47% | 4% | 42% | 0% |

**Note:** The following loglevels were omitted in this report:
* **SKIP**
* **INFO**
* **PASS**
* **DEBUG**
