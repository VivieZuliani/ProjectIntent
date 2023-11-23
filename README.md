# PROJECT INTENT

Nama : Vivie Zuliani Erikasari

NIM : 312210475

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

## Tugas
```
Buatkanlah :

1. Launcher Splash logo masing-masing Individu 

2. Buatkanlah untuk menampilkan semua project sebelum UTS dengan metode Ekplisit Intent dan

     Implisit Intent:

    a. Project Hallo

    b. Project Count

    c. Project Sianida

    d. Project TwoActivity

    e. Project Set Alarm

 
Untuk tampilan Layout Bebas, terima kasih.
```
1. Launcher Splash Logo
Pertama, yaitu membuat Launcher Splash Logo atau menampilkan logo / icon saat kita pertama kali membuka aplikasi.
Caranya :
A. Mempersiapkan logo atau background yang ingin dijadikan Laucher Splash
B. Jika filenya sudah tersedia, copy file lalu paste ke dalam `res`, kemudian `rename` (Pastikan untuk menggunakan huruf kecil semua)
c. Jika sudah selesai maka selanjutnya adalah menuliskan script agar file Launcher Splash Logo bisa muncul ke halaman pengguna.

> Pertama, kita buat  java class nya agar SplashActivity bisa berjalan, lalu pada `SplashActivity.java` kita masukkan kode dibawah ini :
```
package com.example.project;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;

import androidx.appcompat.app.AppCompatActivity;

public class SplashActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent intent = new Intent(SplashActivity.this, MainActivity.class);
                startActivity(intent);
                finish();
            }
        }, 1500);
    }
}

```
> Code di atas digukankan untuk menampilkan SplashScreen, ketika SplashScreen selesai dalam 2.5 detik maka akan langsung berpindah pada tampilan `MainActivity.java`.

- Selanjutnya, buka `AndroidManifest.xml`, kemudian tambahkan kode berikut ke dalam *application* :
```
 <activity
            android:name=".SplashActivity"
            android:exported="true"
            android:theme="@style/Theme.Design.NoActionBar">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
```

Selesai sudah kita membuat perintah Launcher Splash  Logo, Selanjutnya kita akan ke tahap berikutnya yaitu membuat menu untuk menampilkan semua project yang sudah dibuat pada sudah dibuat pada pertemuan sebelumnya.

## 2. Menu Utama
> Yang kedua, disini kita akan membuat menu utamanya yang akan berjalan setelah SplashScreen Logo.
Caranya yaitu :
Jika awal pembuatan project kita memilih template Empty Views Activity, maka pada layout otomatis terbuat file `activity_main.xml` dan pada java akan ada `MainActivity.java`.
Maka langsung saja kita buka `activity_main.xml`, dan buat code seperti berikut ini:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/bground2"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="85dp"
        android:layout_height="16dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.173"/>

    <Button
        android:id="@+id/HelloButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="152dp"
        android:gravity="center_horizontal"
        android:text="Hallo"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/PCount"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.31" />

    <TextView
        android:id="@+id/PSianida"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.201"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.429" />

    <TextView
        android:id="@+id/PTwo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.22"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.567" />

    <TextView
        android:id="@+id/PAlarm"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.715" />

    <Button
        android:id="@+id/CountButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="220dp"
        android:gravity="center_horizontal"
        android:text="Count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/SianidaButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="288dp"
        android:gravity="center_horizontal"
        android:text="Sianida"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/bTwoButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="352dp"
        android:gravity="center_horizontal"
        android:text="Two"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/AlarmButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="420dp"
        android:gravity="center_horizontal"
        android:text="Alarm"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="48dp"
        android:text="Project Intent"
        android:textSize="35dp"
        android:textColor="@color/white"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

- Maka tampilannya akan seperti ini :

  ![](






