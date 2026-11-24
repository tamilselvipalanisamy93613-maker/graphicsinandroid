
# Ex.No:12 Design an application that draws basic graphical primitives on the screen.


## AIM:

To create and design an android application that draws basic graphical primitives on the screen using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “graphical″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Draw basic object details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

/*
Program to create and design an android application that draws basic graphical primitives on the screen.
Developed by: TAMILSELVI P
Registeration Number : 212225040460
*/

## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#ECEFF1">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Graphical Primitives"
        android:textSize="24sp"
        android:textStyle="bold"
        android:textColor="#FFFFFF"
        android:gravity="center"
        android:padding="20dp"
        android:layout_marginTop="30dp"
        android:background="#455A64"/>

    <com.example.graphicalprimitives.DrawingView
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"/>

</LinearLayout>
```
## MainActivity.java:

```
package com.example.graphicalprimitives;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```
## DrawingView.java:
```
package com.example.graphicalprimitives;

import android.content.Context;
import android.graphics.Canvas;
import android.graphics.Paint;
import android.graphics.Color;
import android.util.AttributeSet;
import android.view.View;

public class DrawingView extends View {

    Paint paint;

    public DrawingView(Context context, AttributeSet attrs) {
        super(context, attrs);
        paint = new Paint(Paint.ANTI_ALIAS_FLAG);
        paint.setColor(Color.GRAY);
        paint.setStyle(Paint.Style.FILL);
    }

    @Override
    protected void onDraw(Canvas canvas) {
        super.onDraw(canvas);

        float width = getWidth();
        float height = getHeight();

        float centerX = width / 2;
        float size = width * 0.22f;

        // Circle
        canvas.drawCircle(centerX, height * 0.15f, size, paint);

        // Rectangle
        canvas.drawRect(centerX - size, height * 0.30f,
                centerX + size, height * 0.45f, paint);

        // Line
        paint.setStrokeWidth(20);
        paint.setStyle(Paint.Style.STROKE);
        canvas.drawLine(centerX - size, height * 0.58f,
                centerX + size, height * 0.58f, paint);

        // Oval
        paint.setStyle(Paint.Style.FILL);
        canvas.drawOval(centerX - size, height * 0.70f,
                centerX + size, height * 0.90f, paint);
    }
}
```

## OUTPUT

<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/0b0465c7-9d08-493e-a5de-df5d6921f50a" />



## RESULT
Thus a Simple Android Application to create and design an android application that draws basic graphical primitives on the screen using Android Studio is developed and executed successfully.
