EX:9
import {
IonPage,
IonContent,
IonInput,
IonButton,
IonCard,
IonCardContent
} from '@ionic/react';
import { useState } from 'react';
function Home() {
const [amount, setAmount] = useState("");
const [result, setResult] = useState("");
function addExpense() {
setResult("Expense Added: ₹" + amount);
}
return (
<IonPage>
<IonContent className="ion-padding">
<IonInput
placeholder="Enter Amount"
value={amount}
onIonChange={e => setAmount(e.detail.value!)}
/>
<IonButton onClick={addExpense}>
Add Expense
</IonButton>
<IonCard>
<IonCardContent>
{result}
</IonCardContent>
</IonCard>
</IonContent>
</IonPage>
);
}
export default Home;
EX.NO.:10 UNIT CONVERTER APPLICATION
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical"
android:padding="20dp">
<EditText
android:id="@+id/t1"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:hint="Enter Value"/>
<Button
android:id="@+id/b1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="KM to Miles"/>
<Button
android:id="@+id/b2"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="KG to Pounds"/>
<TextView
android:id="@+id/r1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Result"/>
</LinearLayout>
JAVA
package com.example.myapplication;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.*;
public class MainActivity extends AppCompatActivity {
protected void onCreate(Bundle b) {
super.onCreate(b);
setContentView(R.layout.activity_main);
EditText t1 = findViewById(R.id.t1);
Button b1 = findViewById(R.id.b1);
Button b2 = findViewById(R.id.b2);
TextView r1 = findViewById(R.id.r1);
b1.setOnClickListener(v -> {
double a = Double.parseDouble(t1.getText().toString());
double r = a * 0.621371;
r1.setText("Miles = " + r);
});
b2.setOnClickListener(v -> {
double a = Double.parseDouble(t1.getText().toString());
double r = a * 2.20462;
r1.setText("Pounds = " + r);
});
}
}
EX.NO.:11 TO-DO LIST (TASK MANAGEMENT) APPLICATION
import {
IonPage,
IonContent,
IonInput,
IonButton,
IonList,
IonItem
} from '@ionic/react';
import { useState } from 'react';
function Home() {
const [task, setTask] = useState("");
const [list, setList] = useState<string[]>([]);
function addTask() {
setList([...list, task]);
setTask("");
}
function deleteTask(i: number) {
setList(list.filter((_, index) => index !== i));
}
return (
<IonPage>
<IonContent className="ion-padding">
<IonInput
placeholder="Enter Task"
value={task}
onIonChange={e => setTask(e.detail.value!)}
/>
<IonButton onClick={addTask}>
Add
</IonButton>
<IonList>
{list.map((t, i) => (
<IonItem key={i} onClick={() => deleteTask(i)}>
{t}
</IonItem>
))}
</IonList>
</IonContent>
</IonPage>
);
}
export default Home;
