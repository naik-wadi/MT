
Assignment 3
Q1.
const http = require("http");
const fs = require("fs");
const path = require("path");
const server = http.createServer((req, res) => {
  const filePath = path.join(__dirname, "sample.txt");
  fs.readFile(filePath, "utf8", (err, data) => {
    if (err) {
      res.writeHead(500, { "Content-Type": "text/plain" });
      res.end("Error reading file");
    } else {
      res.writeHead(200, { "Content-Type": "text/plain" });
      res.end(`File Content:\n${data}`);
    }
  });
});
server.listen(3000, () => {
  console.log("Server running at http://localhost:3000");
});
_________________________________******_________________________________
Q2
Math.js
// Custom module: math.js

function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

// Export functions so they can be used in other files
module.exports = {
  add,
  subtract
};

_________
Q2.js
// Import the custom module
const math = require('./math');

console.log('Addition:', math.add(10, 5));       // Output: 15
console.log('Subtraction:', math.subtract(10, 5)); // Output: 5



Q3
npm install express
npm install --save-dev nodemon


const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello from Express!');
});

app.listen(3000, () => {
  console.log('Server running at http://localhost:3000');
});


Q4

const fs = require('fs');

// Read data from input.txt
fs.readFile('input.txt', 'utf8', (err, data) => {
  if (err) {
    return console.error('Error reading file:', err);
  }

  // Process the data (convert to uppercase)
  const processedData = data.toUpperCase();

  // Write processed data to output.txt
  fs.writeFile('output.txt', processedData, (err) => {
    if (err) {
      return console.error('Error writing file:', err);
    }
    console.log('Processed data written to output.txt');
  });
});



Q5

const express = require('express');
const app = express();

// Middleware to parse JSON request bodies
app.use(express.json());

// GET route
app.get('/', (req, res) => {
  res.send('Hello from GET route!');
});

// Another GET route
app.get('/about', (req, res) => {
  res.send('This is the About page.');
});

// POST route
app.post('/data', (req, res) => {
  const body = req.body;
  res.send(`Received data: ${JSON.stringify(body)}`);
});

// Start server
app.listen(3000, () => {
  console.log('Express server running at http://localhost:3000');
});



MT
SAT A  Q1

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal"
    android:padding="16dp">

    <!-- Contact Photo -->
    <ImageView
        android:id="@+id/contact_photo"
        android:layout_width="80dp"
        android:layout_height="80dp"
        android:src="@drawable/ic_person"
        android:contentDescription="Contact Photo"
        android:layout_marginEnd="16dp"/>

    <!-- Info Section -->
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <TextView
            android:id="@+id/contact_name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="John Doe"
            android:textSize="20sp"
            android:textStyle="bold"/>

        <TextView
            android:id="@+id/contact_number"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="+91 9876543210"
            android:textSize="16sp"/>

        <TextView
            android:id="@+id/contact_email"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="johndoe@example.com"
            android:textSize="16sp"/>
    </LinearLayout>
</LinearLayout>


.java
package com.example.contact;



import android.os.Bundle;
import android.widget.ImageView;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    ImageView photo;
    TextView name, number, email;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        photo = findViewById(R.id.contact_photo);
        name = findViewById(R.id.contact_name);
        number = findViewById(R.id.contact_number);
        email = findViewById(R.id.contact_email);

        // Set values programmatically (optional)
        photo.setImageResource(R.drawable.ic_person);
        name.setText("John Doe");
        number.setText("+91 9876543210");
        email.setText("johndoe@example.com");
    }
}



SET A Q2

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <!-- Display -->
    <TextView
        android:id="@+id/display"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="0"
        android:textSize="28sp"
        android:gravity="end"
        android:padding="10dp"
        android:background="#EEEEEE"/>

    <!-- Buttons Grid -->
    <GridLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:columnCount="4"
        android:rowCount="5"
        android:layout_marginTop="20dp">

        <!-- Row 1 -->
        <Button android:id="@+id/btn7" android:text="7"/>
        <Button android:id="@+id/btn8" android:text="8"/>
        <Button android:id="@+id/btn9" android:text="9"/>
        <Button android:id="@+id/btnDiv" android:text="÷"/>

        <!-- Row 2 -->
        <Button android:id="@+id/btn4" android:text="4"/>
        <Button android:id="@+id/btn5" android:text="5"/>
        <Button android:id="@+id/btn6" android:text="6"/>
        <Button android:id="@+id/btnMul" android:text="×"/>

        <!-- Row 3 -->
        <Button android:id="@+id/btn1" android:text="1"/>
        <Button android:id="@+id/btn2" android:text="2"/>
        <Button android:id="@+id/btn3" android:text="3"/>
        <Button android:id="@+id/btnSub" android:text="-"/>

        <!-- Row 4 -->
        <Button android:id="@+id/btn0" android:text="0"/>
        <Button android:id="@+id/btnClear" android:text="C"/>
        <Button android:id="@+id/btnEqual" android:text="="/>
        <Button android:id="@+id/btnAdd" android:text="+"/>
    </GridLayout>
</LinearLayout>

.java
package com.example.calci;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    TextView display;
    String currentInput = "";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        display = findViewById(R.id.display);

        // Number buttons
        int[] numButtons = {R.id.btn0, R.id.btn1, R.id.btn2, R.id.btn3, R.id.btn4,
                R.id.btn5, R.id.btn6, R.id.btn7, R.id.btn8, R.id.btn9};

        for (int id : numButtons) {
            Button b = findViewById(id);
            b.setOnClickListener(v -> {
                currentInput += b.getText().toString();
                display.setText(currentInput);
            });
        }

        // Operators
        findViewById(R.id.btnAdd).setOnClickListener(v -> appendOp("+"));
        findViewById(R.id.btnSub).setOnClickListener(v -> appendOp("-"));
        findViewById(R.id.btnMul).setOnClickListener(v -> appendOp("*"));
        findViewById(R.id.btnDiv).setOnClickListener(v -> appendOp("/"));

        // Clear
        findViewById(R.id.btnClear).setOnClickListener(v -> {
            currentInput = "";
            display.setText("0");
        });

        // Equal
        findViewById(R.id.btnEqual).setOnClickListener(v -> {
            try {
                double result = eval(currentInput);
                display.setText(String.valueOf(result));
                currentInput = String.valueOf(result);
            } catch (Exception e) {
                display.setText("Error");
                currentInput = "";
            }
        });
    }

    private void appendOp(String op) {
        if (!currentInput.isEmpty()) {
            currentInput += op;
            display.setText(currentInput);
        }
    }

    // Simple evaluator: handles one operator between two numbers
    private double eval(String expr) {
        if (expr.contains("+")) {
            String[] t = expr.split("\\+");
            return Double.parseDouble(t[0]) + Double.parseDouble(t[1]);
        } else if (expr.contains("-")) {
            String[] t = expr.split("-");
            return Double.parseDouble(t[0]) - Double.parseDouble(t[1]);
        } else if (expr.contains("*")) {
            String[] t = expr.split("\\*");
            return Double.parseDouble(t[0]) * Double.parseDouble(t[1]);
        } else if (expr.contains("/")) {
            String[] t = expr.split("/");
            return Double.parseDouble(t[0]) / Double.parseDouble(t[1]);
        }
        return 0;
    }
}


SET B Q2

<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fillViewport="true">

    <!-- Inside ScrollView, use a vertical LinearLayout -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <!-- Example content -->
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Vertical Scroll View Example"
            android:textSize="20sp"
            android:textStyle="bold"
            android:layout_marginBottom="20dp"/>

        <!-- Add multiple TextViews to demonstrate scrolling -->
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 1"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 2"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 3"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 4"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 5"/>

        <!-- Add more items to force scrolling -->
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 6"/>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 7"/>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 8"/>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 9"/>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Item 10"/>

    </LinearLayout>
</ScrollView>


.java
package com.example.contactlayout;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}


SET C Q1

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="number"/>

    <EditText
        android:id="@+id/num2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter second number"
        android:inputType="number"/>

    <Button
        android:id="@+id/btnSubmit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Submit"
        android:layout_marginTop="20dp"/>

    <TextView
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Result will appear here"
        android:textSize="18sp"
        android:layout_marginTop="20dp"/>
</LinearLayout>


.java

package com.example.twonum;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    EditText num1, num2;
    Button btnSubmit;
    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        btnSubmit = findViewById(R.id.btnSubmit);
        result = findViewById(R.id.result);

        btnSubmit.setOnClickListener(v -> {
            try {
                int n1 = Integer.parseInt(num1.getText().toString());
                int n2 = Integer.parseInt(num2.getText().toString());

                if (n1 > 10 && n2 > 10) {
                    result.setText("Both numbers are greater than 10. Please enter new numbers.");
                    num1.setText("");
                    num2.setText("");
                } else {
                    result.setText("First Number: " + n1 + "\nSecond Number: " + n2);
                }
            } catch (Exception e) {
                result.setText("Please enter valid numbers.");
            }
        });
    }
}

