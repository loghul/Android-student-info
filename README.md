# Develop a program to accept username and password from the end user using Text View and Edit Text and display personal information of the student.


## AIM:

To develop  application for Student or employee related information and display personal information of the student or employee using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Artic Fox)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as studentinfo and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Accept student name and register number,cgpa from the end user and the display information give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Developed by: Loghul M
Registeration Number : 212220230029
*/
```

```java


## Activity_Main.xml


<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="44dp"
        android:layout_marginTop="80dp"
        android:text="Name"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="44dp"
        android:layout_marginTop="32dp"
        android:text="Reg No"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button" />

    <EditText
        android:id="@+id/e1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="36dp"
        android:layout_marginTop="72dp"
        android:ems="10"
        android:inputType="textPersonName"
        app:layout_constraintStart_toEndOf="@+id/button"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/e2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="36dp"
        android:layout_marginTop="44dp"
        android:ems="10"
        android:inputType="textPersonName"
        app:layout_constraintStart_toEndOf="@+id/button2"
        app:layout_constraintTop_toBottomOf="@+id/e1" />

    <Button
        android:id="@+id/button3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="80dp"
        android:text="submit"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button5"
        app:layout_constraintVertical_bias="0.24" />

    <Button
        android:id="@+id/button4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="112dp"
        android:text="RESET"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.706"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.639" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="237dp"
        android:layout_height="148dp"
        android:layout_marginBottom="52dp"
        android:gravity="center"
        android:textColor="@color/black"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.563"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button3"
        app:layout_constraintVertical_bias="0.622" />

    <Button
        android:id="@+id/button5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="44dp"
        android:layout_marginTop="40dp"
        android:text="CGPA"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button2" />

    <EditText
        android:id="@+id/e3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="44dp"
        android:layout_marginEnd="32dp"
        android:ems="10"
        android:inputType="textPersonName"

        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/e2"
        app:layout_constraintVertical_bias="0.0" />

</androidx.constraintlayout.widget.ConstraintLayout>




##  MainActivity.java



package com.example.studentinformation;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    EditText editName, editregno,editcgpa;
    TextView result;
    Button buttonSubmit, buttonReset;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editName = (EditText) findViewById(R.id.e1);
        editregno = (EditText) findViewById(R.id.e2);
        editcgpa = (EditText) findViewById(R.id.e3);
        result = (TextView) findViewById(R.id.textView);
        buttonSubmit = (Button) findViewById(R.id.button3);
        buttonReset = (Button) findViewById(R.id.button4);
/*
Submit Button
*/
        buttonSubmit.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String name = editName.getText().toString();
                String regno = editregno.getText().toString();
                String cgpa = editcgpa.getText().toString();
                result.setText("Name:\t" + name + "\nReg No:\t" + regno+"\nCGPA:\t"+cgpa );
            }
        });
/*
Reset Button
*/
        buttonReset.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                editName.setText("");
                editregno.setText("");
                editcgpa.setText("");
                result.setText("");
                editName.requestFocus();
            }
        });
    }
}






```

## <br/><br/><br/>OUTPUT
![WhatsApp Image 2022-05-23 at 8 31 58 AM](https://user-images.githubusercontent.com/78194419/172087003-99fa6355-acd2-4201-afb4-6a9d6f706c9a.jpeg)
![WhatsApp Image 2022-05-23 at 8 31 58 AM (1)](https://user-images.githubusercontent.com/78194419/172087013-95c9132d-add8-426f-b8ad-3d40273525ee.jpeg)




## <br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>RESULT
Thus a Simple Android Application  for Student or employee related information and display personal information of the student or employee using  Android Studio is developed and executed successfully.


