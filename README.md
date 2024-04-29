# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

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
Developed by: Reethika S
Registeration Number : 212221040120
*/
```
activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="531dp"
        android:layout_height="374dp"
        app:layout_constraintBottom_toTopOf="@+id/BTNfade"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.397"
        app:srcCompat="@drawable/image2" />

    <Button
        android:id="@+id/BTNblink"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="#52AE56"
        android:text="Blink"
        app:layout_constraintBottom_toTopOf="@+id/BTNmove"
        app:layout_constraintEnd_toStartOf="@+id/BTNrotate"
        app:layout_constraintHorizontal_bias="0.536"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_bias="0.602" />

    <Button
        android:id="@+id/BTNrotate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:backgroundTint="#52AE56"
        android:text="Rotate"
        app:layout_constraintBottom_toTopOf="@+id/BTNslide"
        app:layout_constraintEnd_toStartOf="@+id/BTNfade"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_bias="0.571" />

    <Button
        android:id="@+id/BTNfade"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:backgroundTint="#52AE56"
        android:text="Fade"
        app:layout_constraintBottom_toTopOf="@+id/BTNzoom"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_bias="0.571" />

    <Button
        android:id="@+id/BTNmove"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="48dp"
        android:backgroundTint="#52AE56"
        android:text="Move"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toStartOf="@+id/BTNslide"
        app:layout_constraintHorizontal_bias="0.53"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/BTNslide"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="44dp"
        android:backgroundTint="#52AE56"
        android:text="Slide"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toStartOf="@+id/BTNzoom" />

    <Button
        android:id="@+id/BTNzoom"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="44dp"
        android:backgroundTint="#52AE56"
        android:text="Zoom"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toEndOf="parent" />

    <Button
        android:id="@+id/BTNstop"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="112dp"
        android:backgroundTint="#3FCA45"
        android:text="Stop Animation"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.566"
        app:layout_constraintStart_toStartOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

MainActivity.java

package com.example.animations;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
    ImageView imageView;
    Button blinkBTN, rotateBTN, fadeBTN, moveBTN, slideBTN, zoomBTN, stopBTN;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);
        blinkBTN = findViewById(R.id.BTNblink);
        rotateBTN = findViewById(R.id.BTNrotate);
        fadeBTN = findViewById(R.id.BTNfade);
        moveBTN = findViewById(R.id.BTNmove);
        slideBTN = findViewById(R.id.BTNslide);
        zoomBTN = findViewById(R.id.BTNzoom);
        stopBTN = findViewById(R.id.BTNstop);

        blinkBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add blink animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.blink);
                imageView.startAnimation(animation);
            }
        });

        rotateBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add rotate animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.rotate);
                imageView.startAnimation(animation);
            }
        });

        fadeBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add fade animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.fade);
                imageView.startAnimation(animation);
            }
        });

        moveBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add move animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.move);
                imageView.startAnimation(animation);
            }
        });

        slideBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add slide animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.slide);
                imageView.startAnimation(animation);
            }
        });

        zoomBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add zoom animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
                        R.anim.zoom);
                imageView.startAnimation(animation);
            }
        });

        stopBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To stop the animation going on imageview
                imageView.clearAnimation();
            }
        });
    }
}

move.xml

<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:fromXDelta="0%p"
        android:toXDelta="75%p"
        android:duration="700" />
</set>
blink.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500"
        android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>
fade.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <!-- duration is the time for which animation will work-->
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
rotate.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <rotate
        android:duration="6000"
        android:fromDegrees="0"
        android:pivotX="50%"
        android:pivotY="50%"
        android:toDegrees="360" />
    <rotate
        android:duration="6000"
        android:fromDegrees="360"
        android:pivotX="50%"
        android:pivotY="50%"
        android:startOffset="5000"
        android:toDegrees="0" />
</set>
zoom.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:fromXScale="0.5"
        android:toXScale="3.0"
        android:fromYScale="0.5"
        android:duration="1000"
        android:pivotY="25%"
        android:toYScale="3.0"
        android:pivotX="25%" >
    </scale>
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:startOffset="1000"
        android:fromXScale="3.0"
        android:toXScale="0.5"
        android:toYScale="0.5"
        android:pivotX="25%"
        android:fromYScale="3.0"
        android:duration="1000"
        android:pivotY="25%" >
    </scale>
</set>
slide.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale
        android:duration="500"
        android:fromXScale="1.0"
        android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>

## OUTPUT
![326323450-e937284d-d2eb-4ee6-9b25-5ab02a3b7e55](https://github.com/Ritz514/animation-120/assets/142646304/a2122657-e634-4818-b22c-9b7e05848e04)


![326323466-a2120aba-d5ed-4099-a2a7-fd19a76c1cbc](https://github.com/Ritz514/animation-120/assets/142646304/35bc536e-b9be-456b-84d3-2469f6783455)

![326323490-df1f44a3-e824-4890-a681-f58edffc39f2](https://github.com/Ritz514/animation-120/assets/142646304/7c8d30dc-4544-484c-88de-beb0b88d3e44)

![326323509-a817e10e-9df2-45f5-b55f-9cf087fb8839](https://github.com/Ritz514/animation-120/assets/142646304/6584d700-9fe5-4d8a-938b-0ccb0048314b)

## RESULT
To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio is successful.

