# A3A1

#A3A1 XML
  <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/main"
    android:orientation="vertical"
    android:padding="16dp"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <ImageView
        android:id="@+id/img"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:src="@mipmap/ic_launcher"/>
    <EditText
        android:id="@+id/etName"
        android:hint="Enter Name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
    <EditText
        android:id="@+id/etPhone"
        android:hint="Enter Contact Number"
        android:inputType="phone"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
    <EditText
        android:id="@+id/etEmail"
        android:hint="Enter Email"
        android:inputType="textEmailAddress"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
    <Button
        android:id="@+id/btnSave"
        android:text="Save Contact"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
</LinearLayout>
#java
    package com.example.a3a1;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
    EditText name, phone, email;
    Button save;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        name = findViewById(R.id.etName);
        phone = findViewById(R.id.etPhone);
        email = findViewById(R.id.etEmail);
        save = findViewById(R.id.btnSave);
        save.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this,
                        "Contact Saved Successfully",
                        Toast.LENGTH_SHORT).show();
            }
        });
    }
}




#A3A2

XmL 
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">
    <EditText
        android:id="@+id/display"
        android:layout_width="match_parent"
        android:layout_height="60dp"
        android:textSize="24sp"
        android:gravity="right"
        android:enabled="false"
        android:hint="0"/>
    <TableLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:stretchColumns="*">
        <TableRow>
            <Button android:text="7" android:onClick="numberClick"/>
            <Button android:text="8" android:onClick="numberClick"/>
            <Button android:text="9" android:onClick="numberClick"/>
            <Button android:text="/" android:onClick="operatorClick"/>
        </TableRow>
        <TableRow>
            <Button android:text="4" android:onClick="numberClick"/>
            <Button android:text="5" android:onClick="numberClick"/>
            <Button android:text="6" android:onClick="numberClick"/>
            <Button android:text="*" android:onClick="operatorClick"/>
        </TableRow>
        <TableRow>
            <Button android:text="1" android:onClick="numberClick"/>
            <Button android:text="2" android:onClick="numberClick"/>
            <Button android:text="3" android:onClick="numberClick"/>
            <Button android:text="-" android:onClick="operatorClick"/>
        </TableRow>
        <TableRow>
            <Button android:text="0" android:onClick="numberClick"/>
            <Button android:text="C" android:onClick="clearClick"/>
            <Button android:text="=" android:onClick="equalClick"/>
            <Button android:text="+" android:onClick="operatorClick"/>
        </TableRow>
    </TableLayout>
</LinearLayout>
Java 
package com.example.cal;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
    EditText display;
    double num1, num2;
    String operator;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        display = findViewById(R.id.display);
    }
    public void numberClick(View view) {
        Button b = (Button) view;
        display.append(b.getText().toString());
    }
    public void operatorClick(View view) {
        if(display.getText().toString().isEmpty()){
            Toast.makeText(this,"Enter Number First",
                    Toast.LENGTH_SHORT).show();
            return;
        }
        num1 = Double.parseDouble(display.getText().toString());
        Button b = (Button) view;
        operator = b.getText().toString();
        display.setText("");
    }
    public void equalClick(View view) {
        if(display.getText().toString().isEmpty()) return;
        num2 = Double.parseDouble(display.getText().toString());
        double result = 0;
        if(operator.equals("+"))
            result = num1 + num2;
        else if(operator.equals("-"))
            result = num1 - num2;
        else if(operator.equals("*"))
            result = num1 * num2;
        else if(operator.equals("/"))
            result = num1 / num2;
        display.setText(String.valueOf(result));
    }
    public void clearClick(View view) {
        display.setText("");
    }
}





#A3C



activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">
    <EditText
        android:id="@+id/num1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter First Number"
        android:inputType="number" />
    <EditText
        android:id="@+id/num2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Second Number"
        android:inputType="number" />
    <Button
        android:id="@+id/checkBtn"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Submit" />
    <TextView
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:textSize="18sp"
        android:text="Result will appear here"/>
</LinearLayout>
MainActivity.java
package com.example.setc;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AlertDialog;
public class MainActivity extends AppCompatActivity {
    EditText num1, num2;
    Button checkBtn;
    TextView result;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        checkBtn = findViewById(R.id.checkBtn);
        result = findViewById(R.id.result);
        checkBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if(num1.getText().toString().isEmpty() ||
                        num2.getText().toString().isEmpty()) {
                    Toast.makeText(MainActivity.this,
                            "Enter Both Numbers",
                            Toast.LENGTH_SHORT).show();
                    return;
                }
                int n1 = Integer.parseInt(num1.getText().toString());
                int n2 = Integer.parseInt(num2.getText().toString());
                if(n1 > 10 && n2 > 10) {
                    AlertDialog.Builder builder =
                            new AlertDialog.Builder(MainActivity.this);
                    builder.setTitle("Invalid Input");
                    builder.setMessage("Both numbers are greater than 10.\nEnter 
again.");
        });
    }
}
                    builder.setPositiveButton("OK", null);
                    builder.show();
                    num1.setText("");
                    num2.setText("");
                } else {
                    result.setText("Numbers Accepted:\n"
                            + "Number 1: " + n1
                            + "\nNumber 2: " + n2);
                }
            }


#A3B1




activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">
    <Button
        android:id="@+id/insertBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Insert Contact"/>
</LinearLayout>
📄
ContactActivity.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="20dp"
    android:orientation="vertical">
    <EditText
        android:id="@+id/name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Name"/>
    <EditText
        android:id="@+id/phone"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Mobile"
        android:inputType="phone"/>
    <EditText
        android:id="@+id/email"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Email"
        android:inputType="textEmailAddress"/>
    <Button
        android:id="@+id/saveBtn"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Create Contact"/>
</LinearLayout>
MainActivity.java
package com.example.contactapp;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
public class MainActivity extends AppCompatActivity {
    Button insertBtn;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        insertBtn = findViewById(R.id.insertBtn);
        insertBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent i = new Intent(MainActivity.this,
                        ContactActivity.class);
                startActivity(i);
            }
        });
    }
}
ContactActivity.java
package com.example.contactapp;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
public class ContactActivity extends AppCompatActivity {
    EditText name, phone, email;
    Button saveBtn;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_contact);
        name = findViewById(R.id.name);
        phone = findViewById(R.id.phone);
        email = findViewById(R.id.email);
        saveBtn = findViewById(R.id.saveBtn);
        saveBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if(name.getText().toString().isEmpty() ||
                        phone.getText().toString().isEmpty() ||
                        email.getText().toString().isEmpty()) {
                    Toast.makeText(ContactActivity.this,
                            "Enter All Details",
                            Toast.LENGTH_SHORT).show();
                }
                else {
                    Toast.makeText(ContactActivity.this,
                            "Record Inserted",
                            Toast.LENGTH_LONG).show();
                }
            }
        });
    }
}







#A3B2


activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="20dp">
        <Button android:text="Button 1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 3"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 4"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 5"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 6"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 7"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 8"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 9"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
        <Button android:text="Button 10"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>
    </LinearLayout>
</ScrollView>
MainActivity.java
package com.example.scrollviewapp;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}

