uses-permission android:name="android.permission.CALL_PHONE" 
import android content Intent
import android net Uri
import android os Bundle
import android view View
import android widget Button
import androidx appcompat app AppCompatActivity

public class MainActivity extends AppCompatActivity 
    @Override
    protected void onCreate(Bundle savedInstanceState)
        super onCreate(savedInstanceState)
        setContentView(R layout activity_main)

        Button callButton = findViewById(R id callButton)

        // Butona tıklanma işlemi
        callButton setOnClickListener(new View OnClickListener)
            @Override
            public void onClick(View v) 
                String phoneNumber = "+905432614200"  // Aranacak numara
                Intent callIntent = new Intent(Intent ACTION_CALL)
                callIntent setData(Uri parse)("tel" +905432614200)
                startActivity(callIntent)
                ?xml version="1.0" encoding="utf-8"?>
                <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
                    android layout_width="match_parent"
                    android layout_height="match_parent"
                    android orientation="vertical"
                    android gravity="center"
                    android padding="16dp">
                
                    <Button
                        android id="@+id/callButton"
                        android layout_width="wrap_content"
                        android layout_height="wrap_content"
                        android text="Ara"
                        android textSize="18sp" />
                </LinearLayout>
