# Kotlin MonthAndYearPicker

Month and Year Picker allow user to pick only month and year or only month or only year as required. You will get notified for all action's such as on selection of date, on selection of month and on section of year.

[![](https://jitpack.io/v/gaiththewolf/KotlinMonthAndYearPicker.svg)](https://jitpack.io/#gaiththewolf/KotlinMonthAndYearPicker)
[![Build Status](https://travis-ci.com/gaiththewolf/KotlinMonthAndYearPicker.svg?branch=main)](https://travis-ci.com/gaiththewolf/KotlinMonthAndYearPicker)

# Original repository

https://github.com/premkumarroyal/MonthAndYearPicker

## Usage 

Add Gradle Dependency in your build.gradle file

    implementation 'com.github.gaiththewolf:KotlinMonthAndYearPicker:Tag'

or Maven

    <dependency>
	    <groupId>com.github.gaiththewolf</groupId>
	    <artifactId>KotlinMonthAndYearPicker</artifactId>
	    <version>Tag</version>
	</dependency>
   

# Code

     MonthPickerDialog.Builder(this, object : MonthPickerDialog.OnDateSetListener{
                override fun onDateSet(selectedMonth: Int, selectedYear: Int) {
                    Log.d("MainActivity", "selectedMonth : " + selectedMonth + " selectedYear : " + selectedYear);
                    Toast.makeText(this@MainActivity, "Date set with month" + selectedMonth + " year " + selectedYear, Toast.LENGTH_SHORT).show();
                }
            }, today.get(Calendar.YEAR), today.get(Calendar.MONTH))
                .setMinYear(1990)
                .setActivatedYear(2017)
                .setMaxYear(2030)
                .setMinMonth(Calendar.FEBRUARY)
                .setTitle("Select trading month")
                .setMonthRange(Calendar.FEBRUARY, Calendar.NOVEMBER)
                .setOnMonthChangedListener(object : MonthPickerDialog.OnMonthChangedListener {
                    override fun onMonthChanged(selectedMonth: Int) {
                        Log.d("MainActivity", "Selected month : " + selectedMonth)
                    }
                })
                .setOnYearChangedListener(object : MonthPickerDialog.OnYearChangedListener {
                    override fun onYearChanged(year: Int) {
                        Log.d("MainActivity", "Selected year : " + year)
                    }
                })
                .build()
                .show()
                        
## Listeners
    setOnMonthChangedListener(OnMonthChangedListener());
    setOnYearChangedListener(OnYearChangedListener());

## Methods
 Methods | Docs
------------ | -------------
setMaxMonth(int maxMonth) |  Maximum month that user can select.
setMinMonth(int minMonth) |  Minimum month that user can select.
setMonthRange(int minMonth, int maxMonth) | set both max and min sections.
setActivatedMonth(activatedMonth) | selected the month when picker opens.
setMaxYear(int maxYear) | Maximum year that will be shown in picker.
setMinYear(int minYear) | Minimum year that will be shown in picker.
setYearRange(int minYear, int maxYear) | set both max and min selections.
setActivatedYear(activatedYear) | selected the year when picker opens.
setMonthAndYearRange(int minMonth, int maxMonth, int minYear, int maxYear) | set month and year min and max values at once.
showMonthOnly() | Only month selection will be shown.
showYearOnly() | Only year selection will be shown.
setTitle(String title) | set the title for Month Picker Dialog. By default title will be hidden, it will be visible if value set.
setOnMonthChangedListener(MonthPickerDialog.OnMonthChangedListener onMonthChange); | Listener for select month
setOnYearChangedListener(MonthPickerDialog.OnYearChangedListener onYearChange); | Listener for year select year


## Styling

Month and Year picker by default pick the color from theme if you declared colorAccent. If you want to change color's you can override the theme as below.

     <style name="MonthPickerDialogStyle" >
        <item name="monthBgColor">@color/bgColor</item>
        <item name="monthBgSelectedColor">@color/colorAccent</item>
        <item name="monthFontColorSelected">@color/selectionColor</item>
        <item name="monthFontColorNormal">@color/bgColor</item>
        <item name="monthFontColorDisabled">@color/bgColor</item>

        <item name="headerBgColor">@color/colorAccent</item>
        <item name="headerFontColorSelected">#fff</item>
        <item name="headerFontColorNormal">#85FFFFFF</item>
        <item name="headerTitleColor">#fff</item>

        <item name="dialogActionButtonColor">@color/colorAccent</item>
    </style>


