# Save
Android


Layout

<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.administrador.myapplication.MainActivity">

    <LinearLayout
        android:layout_width="fill_parent"
        android:layout_height="fill_parent"
        android:orientation="vertical"
        android:weightSum="1"
        tools:layout_editor_absoluteX="86dp"
        tools:layout_editor_absoluteY="1dp">

        <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:orientation="horizontal">

            <LinearLayout
                android:layout_width="fill_parent"
                android:layout_height="fill_parent"
                android:orientation="vertical">

                <TextView
                    android:id="@+id/textView"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:background="@android:drawable/screen_background_dark_transparent"
                    android:text="Numero1"
                    tools:layout_editor_absoluteX="36dp"
                    tools:layout_editor_absoluteY="45dp" />

                <EditText
                    android:id="@+id/editText2"
                    android:layout_width="190dp"
                    android:layout_height="46dp"
                    android:background="@android:drawable/editbox_background"
                    android:ems="10"
                    android:inputType="number"
                    tools:layout_editor_absoluteX="36dp"
                    tools:layout_editor_absoluteY="65dp" />


            </LinearLayout>

            <LinearLayout
                android:layout_width="fill_parent"
                android:layout_height="fill_parent"
                android:orientation="vertical">

                <TextView
                    android:id="@+id/textView2"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:background="@android:drawable/screen_background_dark_transparent"
                    android:text="Numero2"
                    tools:layout_editor_absoluteX="206dp"
                    tools:layout_editor_absoluteY="45dp" />

                <EditText
                    android:id="@+id/editText3"
                    android:layout_width="188dp"
                    android:layout_height="match_parent"
                    android:background="@android:drawable/editbox_background"
                    android:ems="10"
                    android:inputType="number"
                    tools:layout_editor_absoluteX="206dp"
                    tools:layout_editor_absoluteY="65dp" />
            </LinearLayout>

        </LinearLayout>

        <EditText
            android:id="@+id/resultado"
            android:layout_width="373dp"
            android:layout_height="wrap_content"
            android:layout_marginBottom="10dp"
            android:background="@android:drawable/editbox_background"
            android:ems="10"
            android:inputType="textPersonName"
            android:text="Resultado" />

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="105dp">

            <Button
                android:id="@+id/Somar"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:autoText="false"
                android:background="@android:drawable/button_onoff_indicator_on"
                android:onClick="Somar"
                android:text="Somar"
                tools:layout_editor_absoluteX="36dp"
                tools:layout_editor_absoluteY="219dp" />

            <Button
                android:id="@+id/Subitração"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="@android:drawable/button_onoff_indicator_off"
                android:onClick="Subitrair"
                android:text="Subtração"
                tools:layout_editor_absoluteX="36dp"
                tools:layout_editor_absoluteY="219dp" />
        </LinearLayout>

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="105dp">

            <Button
                android:id="@+id/Divsão"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="@android:drawable/button_onoff_indicator_off"
                android:onClick="Dividir"
                android:text="Divisão"
                tools:layout_editor_absoluteX="36dp"
                tools:layout_editor_absoluteY="219dp" />

            <Button
                android:id="@+id/Multiplicação"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="@android:drawable/button_onoff_indicator_on"
                android:onClick="Multiplicar"
                android:text="Multiplicar"
                tools:layout_editor_absoluteX="36dp"
                tools:layout_editor_absoluteY="219dp" />

        </LinearLayout>


    </LinearLayout>
</android.support.constraint.ConstraintLayout>

*********************************************************************************************************************************************
MainActivy

package com.example.administrador.myapplication;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void Somar(View view) {
        EditText editText2 = (EditText) findViewById(R.id.editText2);
        EditText editText3 = (EditText) findViewById(R.id.editText3);
        EditText Rs = (EditText) findViewById(R.id.resultado);

        Double calcular = Double.valueOf(editText2.getText().toString()) +
                Double.valueOf(editText3.getText().toString());

        Rs.setText("" + calcular);
        Toast.makeText(this, "sucesso", Toast.LENGTH_LONG).show();
    }

    public void Subitrair(View view) {

        EditText editText2 = (EditText) findViewById(R.id.editText2);
        EditText editText3 = (EditText) findViewById(R.id.editText3);
        EditText Rs = (EditText) findViewById(R.id.resultado);

        Double calcular = Double.valueOf(editText2.getText().toString()) -
                Double.valueOf(editText3.getText().toString());

        Rs.setText("" + calcular);
        Toast.makeText(this, "sucesso", Toast.LENGTH_LONG).show();
    }

    public void Dividir(View view) {
        EditText editText2 = (EditText) findViewById(R.id.editText2);
        EditText editText3 = (EditText) findViewById(R.id.editText3);
        EditText Rs = (EditText) findViewById(R.id.resultado);

        Double calcular = Double.valueOf(editText2.getText().toString()) /
                Double.valueOf(editText3.getText().toString());

        Rs.setText("" + calcular);
        Toast.makeText(this, "sucesso", Toast.LENGTH_LONG).show();
    }

    public void Multiplicar(View view) {

        EditText editText2 = (EditText) findViewById(R.id.editText2);
        EditText editText3 = (EditText) findViewById(R.id.editText3);
        EditText Rs = (EditText) findViewById(R.id.resultado);

        Double calcular = Double.valueOf(editText2.getText().toString()) *
                Double.valueOf(editText3.getText().toString());

        Rs.setText("" + calcular);
        Toast.makeText(this, "sucesso", Toast.LENGTH_LONG).show();
    }
}







