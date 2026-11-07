# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.
## DATE : 30.10.26

## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. **Create Layout** – Add an `EditText` for URL input and a `Button` labeled "Navigate".
2. **Initialize Components** – Link `EditText` and `Button` with `findViewById()`.
3. **Set Listener** – Attach `onClickListener` to the "Navigate" button.
4. **Get Input** – Read the text from `EditText` when button is clicked.
5. **Create Intent** – Use `Intent.ACTION_VIEW` with `Uri.parse()` of the entered URL.
6. **Start Activity** – Call `startActivity(intent)` to open the browser page.



## PROGRAM:

Program to print the text “Implicitintent”.
```
Developed by: M MOHAMED ASHFAQ
Registeration Number : 212224240090
```

## MAINACTIVITY:

```

package com.example.implicitintent;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editTextText);
        button = findViewById(R.id.btn);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String url = editText.getText().toString().trim();

                if (url.isEmpty()) {
                    Toast.makeText(MainActivity.this,
                            "Enter URL", Toast.LENGTH_SHORT).show();
                    return;
                }

                if (!url.startsWith("https://") &&
                        !url.startsWith("http://")) {
                    url = "https://" + url;
                }

                Intent intent = new Intent(
                        Intent.ACTION_VIEW,
                        Uri.parse(url)
                );

                startActivity(intent);
            }
        });
    }
}

```



## ACTIVITY_MAIN.XML:

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#99E91E58"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="IMPLICIT INTENT"
        android:textSize="30sp"
        android:textStyle="bold"
        android:textColor="#000000"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="150dp"/>

    <EditText
        android:id="@+id/editTextText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_margin="30dp"
        android:hint="ENTER THE URL"
        android:inputType="textUri"
        android:textSize="18sp"
        app:layout_constraintTop_toBottomOf="@id/textView"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="NAVIGATE"
        android:textSize="20sp"
        app:layout_constraintTop_toBottomOf="@id/editTextText"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>

```

## OUTPUT
<img width="2560" height="1440" alt="Screenshot 2026-11-07 183610_edited" src="https://github.com/user-attachments/assets/435dad9e-385f-4fd6-b06e-dc8e9ecf6944" />

## DESGINING:
<img width="2560" height="1440" alt="Screenshot 2026-11-07 183902_edited" src="https://github.com/user-attachments/assets/26b3eef4-036d-4287-a50b-34ec70cbcc8a" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


