# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Artic Fox)

## ALGORITHM:
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as "androidanimation" and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Create a anim folder under res and create the xml files for the animation operators.

Step 7: Add animation operations in MainActivity file.

Step 8: Save and run the application.


## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: sivaragul.m
Registeration Number : 212221040155
*/
```
#### MainActivity.java
```
package com.example.androidanimation;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.ImageView;
import android.view.View;


public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void clockwise(View view){
        ImageView image = (ImageView)findViewById(R.id.imageView);
        Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                R.anim.myanimation);
        image.startAnimation(animation);
    }

    public void zoom(View view){
        ImageView image = (ImageView)findViewById(R.id.imageView);
        Animation animation1 = AnimationUtils.loadAnimation(getApplicationContext(),
                R.anim.clockwise);
        image.startAnimation(animation1);
    }

    public void fade(View view){
        ImageView image = (ImageView)findViewById(R.id.imageView);
        Animation animation1 =
                AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.fade);
        image.startAnimation(animation1);
    }

    public void blink(View view){
        ImageView image = (ImageView)findViewById(R.id.imageView);
        Animation animation1 =
                AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.blink);
        image.startAnimation(animation1);
    }

    public void move(View view){
        ImageView image = (ImageView)findViewById(R.id.imageView);
        Animation animation1 =
                AnimationUtils.loadAnimation(getApplicationContext(), R.anim.move);
        image.startAnimation(animation1);
    }

    public void slide(View view){
        ImageView image = (ImageView)findViewById(R.id.imageView);
        Animation animation1 =
                AnimationUtils.loadAnimation(getApplicationContext(), R.anim.slide);
        image.startAnimation(animation1);
    }
}
```
#### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:paddingLeft="20dp"
    android:paddingRight="20dp"
    android:paddingTop="20dp"
    android:paddingBottom="20dp"
    tools:context=".MainActivity">

<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Animation"
    android:id="@+id/textView"
    android:textSize="35dp"
    android:layout_alignParentTop="true"
    android:layout_centerHorizontal="true"
    />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="20dp"
        android:layout_height="100dp"
        android:paddingTop="10dp"
        android:layout_below="@+id/textView"
        android:layout_alignRight="@+id/textView"
        android:layout_alignEnd="@+id/textView"
        android:layout_alignLeft="@+id/textView"
        android:layout_alignStart="@+id/textView"
        app:srcCompat="@android:drawable/btn_star_big_on" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="zoom"
        android:id="@+id/button"
        android:layout_below="@+id/imageView"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true"
        android:layout_marginTop="40dp"
        android:onClick="clockwise"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="clockwise"
        android:id="@+id/button2"
        android:layout_alignTop="@+id/button"
        android:layout_centerHorizontal="true"
        android:onClick="zoom"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="fade"
        android:id="@+id/button3"
        android:layout_alignTop="@+id/button2"
        android:layout_alignParentRight="true"
        android:layout_alignParentEnd="true"
        android:onClick="fade"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="blink"
        android:onClick="blink"
        android:id="@+id/button4"
        android:layout_below="@+id/button"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="move"
        android:onClick="move"
        android:id="@+id/button5"
        android:layout_below="@+id/button2"
        android:layout_alignRight="@+id/button2"
        android:layout_alignEnd="@+id/button2"
        android:layout_alignLeft="@+id/button2"
        android:layout_alignStart="@+id/button2" />

    <Button
        android:id="@+id/button6"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/button3"
        android:layout_marginStart="21dp"
        android:layout_marginLeft="21dp"
        android:layout_marginTop="4dp"
        android:layout_toEndOf="@+id/textView"
        android:layout_toRightOf="@+id/textView"
        android:onClick="slide"
        android:text="slide" />

</RelativeLayout>
```
#### myanimation.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="0.5"
    android:toXScale="3.0"
    android:fromYScale="0.5"
    android:toYScale="3.0"
    android:duration="5000"
    android:pivotX="50%"
    android:pivotY="50%" >
    </scale>

    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:startOffset="5000"
        android:fromXScale="3.0"
        android:toXScale="0.5"
        android:fromYScale="3.0"
        android:toYScale="0.5"
        android:duration="5000"
        android:pivotX="50%"
        android:pivotY="50%" >
        </scale>
        </set>
````
#### move.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/linear_interpolator"
    android:fillAfter="true">

    <translate
        android:fromXDelta="0%p"
        android:toXDelta="75%p"
        android:duration="700" />
</set>
```
#### blink.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500"
        android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>
```
#### fade.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/accelerate_interpolator">

    <alpha
        android:duration="1000"
        android:fromAlpha="0"
        android:toAlpha="1" />

    <alpha
        android:duration="1000"
        android:fromAlpha="1"
        android:startOffset="2000"
        android:toAlpha="0" />

</set>
```
#### clockwise.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">

<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="5000" >
    </rotate>

    <rotate xmlns:android="http://schemas.android.com/apk/res/android"
        android:startOffset="5000"
        android:fromDegrees="360"
        android:toDegrees="0"
        android:pivotX="50%"
        android:pivotY="50%"
        android:duration="5000" >
        </rotate>
        </set>
```
#### zoom.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >

    <scale
        android:duration="500"
        android:fromXScale="1.0"
        android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>
```
#### slide.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >
    <scale
        android:duration="500"
        android:fromXScale="1.0"
        android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>
```
## OUTPUT
![9 1](https://user-images.githubusercontent.com/94883876/203524920-8c16080d-20d0-4193-bf73-e3b19b964a1d.jpg)
![9 2](https://user-images.githubusercontent.com/94883876/203524930-5592951d-51be-4e3f-9739-3df59554d087.jpg)
![9 3](https://user-images.githubusercontent.com/94883876/203524940-80fa7e80-adc9-4462-8378-a6c22af181af.jpg)
![9 4](https://user-images.githubusercontent.com/94883876/203524949-0762861d-fdab-4dbb-9458-aa115149ff39.jpg)
![9 5](https://user-images.githubusercontent.com/94883876/203524960-e7aba0f8-825e-4380-b890-0d551cabf55e.jpg)
![9 6](https://user-images.githubusercontent.com/94883876/203524977-980caeeb-319a-4a80-8c14-7874710d6e39.jpg)



## RESULT
Thus a Simple Android Application to add animations: Move,blink,fade,clockwise,zoom,slide operations using Android Studio is developed and executed successfully.
