# ACN-Final-Score-App/ Customized Buttons

/** One have to create a new XML FILE in the DRAWABLE FOLDER which will contain the codes below
/ the codes below can be adjusted depending on what the user which to make out of it. 
/After which the user call it as a drawable file in the MAIN XML FILE. Eg. let the name of the below code file be 
/customized_button.xml. The button in the main XML file where u need it, apply it as the background i.e 'android:background="@drawable/customized_button"


<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item>
        <shape android:shape="rectangle"  >
            <corners android:bottomLeftRadius="500dp"
                android:bottomRightRadius="10dp"
                android:topLeftRadius="100dp"
                android:topRightRadius="0dp"  />
            <stroke android:width="1dip"
                android:color="#667162" />
            <gradient android:angle="-90"
                android:startColor="#827717"
                android:endColor="#ffffff" />
        </shape>
    </item>
</selector>
