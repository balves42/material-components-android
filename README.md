# Material Components for Android (+ Date Range Custom fields)

A fork of the Material Components for Android which intends to guarantee that a custom locale and more custom text can be provided.

## Added features

<img src="https://imgur.com/SPFO3Sh.jpg" title="source: imgur.com" /></a>

1. Confirm button
2. Title (already existed)
3. Header
4. "Month, year" and "Days of the week"
    * Generated with the given locale or default

## Usage

For example, when building the MaterialDatePicker:
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

[Don't forget to look for other ISO codes and add them to the locale](http://www.lingoes.net/en/translator/langcode.htm)

## Limitations
Only tested for the Date Range Picker. Feel free to report any bugs detected to other components.
