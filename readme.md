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
March 2020
