# AdditionApp
# Android application for addition of two numbers.
## AIM

To create an Android application to get two numbers and display their sum in a TextView using Android Studio.

## PROCEDURE

1. Create a new project in Android Studio using Empty Views Activity.
2. Design the user interface using XML with two EditText fields, one Button and one TextView.
3. Enter the first and second numbers in the EditText fields.
4. Create a Button to perform the addition operation.
5. Write Java code to retrieve the entered numbers and calculate their sum.
6. Display the summation value in the TextView.
7. Run the application using an emulator and verify the output.

## XML CODE (activity_main.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center">

    <EditText
        android:id="@+id/num1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter First Number"
        android:inputType="numberDecimal" />

    <EditText
        android:id="@+id/num2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Second Number"
        android:inputType="numberDecimal" />

    <Button
        android:id="@+id/addButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="ADD" />

    <TextView
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Result"
        android:textSize="24sp"
        android:gravity="center"
        android:padding="20dp" />

</LinearLayout>
```

## JAVA CODE (MainActivity.java)

```java
package com.example.additionapp;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText num1, num2;
    Button addButton;
    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        addButton = findViewById(R.id.addButton);
        result = findViewById(R.id.result);

        addButton.setOnClickListener(v -> {

            String a = num1.getText().toString();
            String b = num2.getText().toString();

            if (!a.isEmpty() && !b.isEmpty()) {
                double n1 = Double.parseDouble(a);
                double n2 = Double.parseDouble(b);

                double sum = n1 + n2;

                result.setText("Sum = " + sum);
            } else {
                result.setText("Enter both numbers");
            }
        });
    }
}
```

## OUTPUT

Enter the first number and the second number in the input fields and click the ADD button. The summation value is displayed in the TextView.

<img width="1920" height="1080" alt="Screenshot (290)" src="https://github.com/user-attachments/assets/3f77768e-ca5d-4aa3-abda-cb84d3d16d84" />


**Example:**

First Number: 602

Second Number: 278

Result: Sum = 880.0

## RESULT

Thus, the Android application for addition of two numbers was created and executed successfully.
