Date Range Picker 
===================
Date Range Picker is an extension of Square Calender Picker View to show a Customized Date Range Picker with improved UI

Screenshots
-----------
<img src="device-2017-06-23-154706.png" alt="alt text" width="300" height="500"> <img src="device-2017-06-23-154757.png" alt="alt text" width="300" height="500">

Usage
-----
* 1. Add Calendar Picker View to XML

```xml
<com.savvi.rangepicker.CalendarPickerView
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:id="@+id/calendar_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:paddingLeft="16dp"
        android:paddingRight="16dp"
        android:paddingBottom="16dp"
        android:scrollbarStyle="outsideOverlay"
        android:clipToPadding="false"
        app:tsquare_dividerColor="@color/transparent"
        app:tsquare_headerTextColor="@color/custom_header_text"
        /> 
 ```
 
* 2. Initialize it in Java Class

```java
calendar = (CalendarPickerView) findViewById(R.id.calendar_view);

        calendar.init(lastYear.getTime(), nextYear.getTime()) //
                .inMode(CalendarPickerView.SelectionMode.RANGE) //
                .withSelectedDate(new Date());
 
```

* Adding Unavailable Dates
  These dates will be shown in Red color and marked unavailable

```java
ArrayList<Date> arrayList = new ArrayList<>();
//add dates which you want to unavailable
calendar.highlightDates(arrayList);

 ``` 
 
 * Adding Deactivated Dates
  User wont able to select these dates thwy will be deactivated.
  for eg, if you dont want to provide services on Saturday and Sunday you can mark them deactivated with grey color

```java
ArrayList<Integer> list = new ArrayList<>();
        list.add(1);
        list.add(7);
        
calendar.deactivateDates(list);

 ``` 
 
 * Getting Selected Dates
You can get selected dates with the below function call when your user click finish or next button(which will you implement)
Dont forget to exclude Unavailable dates from the selected dates, its a bug so I will soon fix it.

```java

calendar.getSelectedDates()

 ``` 
 
 Import DateRangePicker dependency
------------------------------------

declare it into your pom.xml

```xml
<dependency>
  <groupId>com.savvi.rangepicker</groupId>
  <artifactId>rangepicker</artifactId>
  <version>1.0.1</version>
  <type>pom</type>
</dependency>
```
or into your build.gradle

```groovy
dependencies {
    compile 'com.savvi.rangepicker:rangepicker:1.0.1'
}
```
