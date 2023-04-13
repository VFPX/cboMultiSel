VFP Component Class cboMultiSel
===============================
Multi-Select Combobox Control
-----------------------------

![Image of control](images/pic1.jpg)


A class that defines a combo-style control for selecting multiple values from a list and storing as a single, character-separated string. This was inspired by, and is a total rebuild of, a similar control floating around: "multiSelCombo".

The class is designed to be all-in-one (clutter-free) where there are no secondary/ancillary files required beyond the FoxPro and Windows APIs.

Usage, briefly:

	* Drop this control on a form and configure its rowSource property (must be 2-alias, 3-SQL statement, or 6-fields)
	* Configure the instance, say, from an init event:

		.RowSourceType=6					&& Fields
		.ControlSource="Thisform.mySels"	&& what we'll bind the value to
		.ColumnWidths = "15, 200"	
		.srcValCol = "CD"					&& data source column/field to use for the values
		.srcDispCol = "NME"					&& data source column to use for the display values
		.valDelim = "'"						&& optional delimiter to surround selected values with
		.srcColTitls = "Code, Name" 		&& titles for the columns (if headers are shown)
		.RowSource = "CSRC.CD, NME"			&& the data columns for the picklist (set this  last)

See the accompanying test form, **cboMultiSelTest.sc?**, for complete examples.

![Image of test screen](images/pic2.jpg)

G. Willcockson

## Releases

### 2023-04-12

Enhanced to includes the following:

- Ability to paste a separated value string into the combo which will select values in the underlying list.

> - Values in the separated value string that don't have a match in the defining list will be removed

- Typing characters while focused on the control can fire the dropdown and search for the typed character(s).

> - Requires specifying up to two data column indexes that will be used for value compares (via LOCATE)
> - Only valid for text based column values - characters 0-9, a-Z
> - Match is case-insensitive
> - Match is from the beginning of the value: substring  matches not (yet) supported
> - Matching starts over at beginning of list after no more matches

### 2022-07-11

* Fixed not being able to close the form using Thisform.Release after opening the combobox.
* Add text equivalents of binary files to the repository.

### 2020-07-24

* Updated documentation

### March 2020

* Initial release
