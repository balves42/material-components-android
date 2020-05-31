# Material Components for Android (+ Date Range Custom fields)

A fork of the Material Components for Android which intends to guarantee that a custom locale and more custom text can be provided. Livedata can be also used to perform range selection checks.
Check [balves42/DateRangePickerDemo](https://github.com/balves42/DateRangePickerDemo) for a naive implementation.

## Added features
<img src="https://imgur.com/SPFO3Sh.jpg" title="Custom fields added" /></a>

1. Confirm button
2. Title (already existed)
3. Header
4. "Month, year" and "Days of the week"
    * Generated with the given locale or default

## Usage

### Without live data
~~~~~
//Add to your app build.gradle
implementation "com.github.balves42:material-components-android:1.2.0-beta01-customtext"
~~~~~

For example, when building the date range picker:
~~~~~
val builder = MaterialDatePicker.Builder.dateRangePicker()
builder.setTitleText("Titulo")
builder.setHeaderText("Inicio", "Fim")
builder.setConfirmText("Botao")
builder.setLocale("pt")
~~~~~

And then simply call it:
~~~~~~
val materialDatePicker = builder.build()
materialDatePicker.show(fragmentManager, materialDatePicker.string)
~~~~~~

### With live data
<img src="https://i.imgur.com/dfxrnXq.gif" title="Toast showing max range error" /></a>

~~~~~
//Add to your app build.gradle
implementation "com.github.balves42:material-components-android:1.2.0-beta01-ct-live"
~~~~~

After showing the materialDatePicker, simply call:
~~~~~
mMaterialDatePicker?.selectionLive.observe(lifecycleOwner, Observer { pair ->
  //Behaviour performed when range is selected. Perform validations if needed.
})
~~~~~

[Don't forget to look for the ISO codes when you want to provide a custom locale](http://www.lingoes.net/en/translator/langcode.htm)

## Limitations
Only tested for the Date Range Picker. Feel free to report any bugs detected to other components.
