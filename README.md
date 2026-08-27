Ex.No:5 Develop a simple calculator using android studio.
AIM:
To develop a program to develop a simple calculator in Android Studio.

EQUIPMENTS REQUIRED:
Android Studio(Min.required Artic Fox)

ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Display the calculator operation in MainActivity file.

Step 7: Save and run the application.

PROGRAM:
/* Program to print the text “calculator operation”. Developed by: GANESH PRABHU J Registeration Number : 212223220023 */

MainActivity.java:
package com.example.calculatorapp;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TextView tvDisplay;

    double firstNumber = 0;
    double secondNumber = 0;

    String operator = "";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

        tvDisplay = findViewById(R.id.tvDisplay);

        // Number buttons
        findViewById(R.id.btn0).setOnClickListener(v -> addNumber("0"));
        findViewById(R.id.btn1).setOnClickListener(v -> addNumber("1"));
        findViewById(R.id.btn2).setOnClickListener(v -> addNumber("2"));
        findViewById(R.id.btn3).setOnClickListener(v -> addNumber("3"));
        findViewById(R.id.btn4).setOnClickListener(v -> addNumber("4"));
        findViewById(R.id.btn5).setOnClickListener(v -> addNumber("5"));
        findViewById(R.id.btn6).setOnClickListener(v -> addNumber("6"));
        findViewById(R.id.btn7).setOnClickListener(v -> addNumber("7"));
        findViewById(R.id.btn8).setOnClickListener(v -> addNumber("8"));
        findViewById(R.id.btn9).setOnClickListener(v -> addNumber("9"));

        // Operators
        findViewById(R.id.btnPlus).setOnClickListener(v -> setOperator("+"));
        findViewById(R.id.btnMinus).setOnClickListener(v -> setOperator("-"));
        findViewById(R.id.btnMultiply).setOnClickListener(v -> setOperator("*"));
        findViewById(R.id.btnDivide).setOnClickListener(v -> setOperator("/"));

        // Equal
        findViewById(R.id.btnEqual).setOnClickListener(v -> calculate());

        // Clear
        findViewById(R.id.btnClear).setOnClickListener(v -> clear());
    }

    // Add number to display
    private void addNumber(String number) {

        String current = tvDisplay.getText().toString();

        if (current.equals("0")) {
            tvDisplay.setText(number);
        } else {
            tvDisplay.append(number);
        }
    }

    // Store first number and operator
    private void setOperator(String op) {

        firstNumber = Double.parseDouble(
                tvDisplay.getText().toString()
        );

        operator = op;

        tvDisplay.setText("0");
    }

    // Perform calculation
    private void calculate() {

        secondNumber = Double.parseDouble(
                tvDisplay.getText().toString()
        );

        double result = 0;

        switch (operator) {

            case "+":
                result = firstNumber + secondNumber;
                break;

            case "-":
                result = firstNumber - secondNumber;
                break;

            case "*":
                result = firstNumber * secondNumber;
                break;

            case "/":

                if (secondNumber == 0) {
                    tvDisplay.setText("Error");
                    return;
                }

                result = firstNumber / secondNumber;
                break;
        }

        tvDisplay.setText(String.valueOf(result));
    }

    // Clear calculator
    private void clear() {

        firstNumber = 0;
        secondNumber = 0;
        operator = "";

        tvDisplay.setText("0");
    }
}

activity_main.xml:
package com.example.calculatorapp;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TextView tvDisplay;

    double firstNumber = 0;
    double secondNumber = 0;

    String operator = "";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

        tvDisplay = findViewById(R.id.tvDisplay);

        // Number buttons
        findViewById(R.id.btn0).setOnClickListener(v -> addNumber("0"));
        findViewById(R.id.btn1).setOnClickListener(v -> addNumber("1"));
        findViewById(R.id.btn2).setOnClickListener(v -> addNumber("2"));
        findViewById(R.id.btn3).setOnClickListener(v -> addNumber("3"));
        findViewById(R.id.btn4).setOnClickListener(v -> addNumber("4"));
        findViewById(R.id.btn5).setOnClickListener(v -> addNumber("5"));
        findViewById(R.id.btn6).setOnClickListener(v -> addNumber("6"));
        findViewById(R.id.btn7).setOnClickListener(v -> addNumber("7"));
        findViewById(R.id.btn8).setOnClickListener(v -> addNumber("8"));
        findViewById(R.id.btn9).setOnClickListener(v -> addNumber("9"));

        // Operators
        findViewById(R.id.btnPlus).setOnClickListener(v -> setOperator("+"));
        findViewById(R.id.btnMinus).setOnClickListener(v -> setOperator("-"));
        findViewById(R.id.btnMultiply).setOnClickListener(v -> setOperator("*"));
        findViewById(R.id.btnDivide).setOnClickListener(v -> setOperator("/"));

        // Equal
        findViewById(R.id.btnEqual).setOnClickListener(v -> calculate());

        // Clear
        findViewById(R.id.btnClear).setOnClickListener(v -> clear());
    }

    // Add number to display
    private void addNumber(String number) {

        String current = tvDisplay.getText().toString();

        if (current.equals("0")) {
            tvDisplay.setText(number);
        } else {
            tvDisplay.append(number);
        }
    }

    // Store first number and operator
    private void setOperator(String op) {

        firstNumber = Double.parseDouble(
                tvDisplay.getText().toString()
        );

        operator = op;

        tvDisplay.setText("0");
    }

    // Perform calculation
    private void calculate() {

        secondNumber = Double.parseDouble(
                tvDisplay.getText().toString()
        );

        double result = 0;

        switch (operator) {

            case "+":
                result = firstNumber + secondNumber;
                break;

            case "-":
                result = firstNumber - secondNumber;
                break;

            case "*":
                result = firstNumber * secondNumber;
                break;

            case "/":

                if (secondNumber == 0) {
                    tvDisplay.setText("Error");
                    return;
                }

                result = firstNumber / secondNumber;
                break;
        }

        tvDisplay.setText(String.valueOf(result));
    }

    // Clear calculator
    private void clear() {

        firstNumber = 0;
        secondNumber = 0;
        operator = "";

        tvDisplay.setText("0");
    }
}

OUTPUT:


<img width="1919" height="1006" alt="640806087-3b772cc9-d759-401c-bf2e-39e25eb5e584" src="https://github.com/user-attachments/assets/e529f45c-0c33-4e30-874e-bf9238442c61" />

RESULT:
Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.

