
# Ex.No:7 Design an application that draws basic graphical primitives on the screen.


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
        paint.setTextSize(40);
    }

    @Override
    protected void onDraw(Canvas canvas) {
        super.onDraw(canvas);

        float width = getWidth();
        float height = getHeight();
        float centerX = width / 2;
        float size = width * 0.18f;

        // Circle
        paint.setStyle(Paint.Style.FILL);
        paint.setColor(Color.GRAY);
        canvas.drawCircle(centerX, height * 0.12f, size, paint);

        paint.setColor(Color.BLACK);
        paint.setTextAlign(Paint.Align.CENTER);
        canvas.drawText("Circle", centerX, height * 0.24f, paint);

        // Rectangle
        paint.setColor(Color.GRAY);
        canvas.drawRect(centerX - size, height * 0.30f,
                centerX + size, height * 0.42f, paint);

        paint.setColor(Color.BLACK);
        canvas.drawText("Rectangle", centerX, height * 0.46f, paint);

        // Line
        paint.setColor(Color.GRAY);
        paint.setStyle(Paint.Style.STROKE);
        paint.setStrokeWidth(15);
        canvas.drawLine(centerX - size, height * 0.56f,
                centerX + size, height * 0.56f, paint);

        paint.setStyle(Paint.Style.FILL);
        paint.setColor(Color.BLACK);
        canvas.drawText("Line", centerX, height * 0.62f, paint);

        // Square
        paint.setColor(Color.GRAY);
        canvas.drawRect(centerX - size, height * 0.70f,
                centerX + size, height * 0.70f + (size * 2), paint);

        paint.setColor(Color.BLACK);
        canvas.drawText("Square", centerX, height * 0.70f + (size * 2) + 50, paint);
    }
}
```

## OUTPUT

<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/28279274-df6d-4c73-a4e0-0d08774bb73f" />



## RESULT
Thus a Simple Android Application to create and design an android application that draws basic graphical primitives on the screen using Android Studio is developed and executed successfully.
