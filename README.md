# Android5.1
mainactivity
  package com.example.pankaj.menu51;

import android.app.Activity;
import android.content.Context;
import android.graphics.Color;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.widget.RelativeLayout;
import android.widget.TextView;
import android.support.v7.widget.Toolbar;


public class MainActivity extends AppCompatActivity {
    private Context mContext;
    private Activity mActivity;

    private RelativeLayout mRelativeLayout;
    private TextView mTextView;
    private Toolbar mToolbar;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Get the application context
        mContext = getApplicationContext();
        // Get the activity
        mActivity = MainActivity.this;

        // Get the widgets reference from XML layout
        mRelativeLayout = (RelativeLayout) findViewById(R.id.rl);
        mTextView = (TextView) findViewById(R.id.tv);
        mToolbar = (Toolbar) findViewById(R.id.toolbar);

        // Set a title for toolbar
        mToolbar.setTitle("Android Options Menu Example");
        mToolbar.setTitleTextColor(Color.WHITE);

        // Set support actionbar with toolbar
        setSupportActionBar(mToolbar);

        // Change the toolbar background color
        mToolbar.setBackgroundColor(Color.parseColor("#FF80D7FF"));
    }
    @Override
    public boolean onCreateOptionsMenu(Menu menu){

        MenuInflater inflater = getMenuInflater();
        inflater.inflate(R.menu.toolbar_options_menu, menu);
        return true;
    }



    @Override
    public boolean onOptionsItemSelected(MenuItem item){
        switch(item.getItemId()){
            case R.id.red:
                // Set the text color to red
                mTextView.setTextColor(Color.RED);
                return true;
            case R.id.green:
                // Set the text color to green
                mTextView.setTextColor(Color.GREEN);
                return true;
            case R.id.blue:
                // Set the text color to blue
                mTextView.setTextColor(Color.BLUE);
                return true;
            case R.id.maroon:
                // Set the text color to maroon
                mTextView.setTextColor(Color.parseColor("#800000"));
                return true;
            case R.id.orange:
                // Set the text color to orange
                mTextView.setTextColor(Color.parseColor("#FFA500"));
                return true;
            case R.id.purple:
                // Set the text color to purple
                mTextView.setTextColor(Color.parseColor("#800080"));
                return true;
            case R.id.black:
                // Set the text color to black
                mTextView.setTextColor(Color.BLACK);
                return true;
            default:
                return super.onOptionsItemSelected(item);
        }
    }
}
-------------------------------
activity
  <?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/rl"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="0dp"
    tools:context=".MainActivity"
    android:background="#fcfdfb"
    >
    <android.support.v7.widget.Toolbar
        android:id="@+id/toolbar"
        android:layout_width="match_parent"
        android:layout_height="?attr/actionBarSize"
        android:background="?attr/colorPrimary"
        android:elevation="4dp"
        android:theme="@style/ThemeOverlay.AppCompat.ActionBar"
        app:popupTheme="@style/ThemeOverlay.AppCompat.Light"
        />
    <TextView
        android:id="@+id/tv"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Change This Text Color\nUsing Toolbar Menu"
        android:textSize="50dp"
        android:gravity="center"
        android:textStyle="bold"
        />

</RelativeLayout>
------------------------------------------
tool
  <?xml version="1.0" encoding="utf-8"?>
<menu
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    >
    <item
        android:id="@+id/red"
        android:title="Red"
        app:showAsAction="always|withText"
        android:orderInCategory="1"
        />
    <item
        android:id="@+id/green"
        android:title="Green"
        app:showAsAction="ifRoom|withText"
        android:orderInCategory="2"
        />
    <item
        android:id="@+id/blue"
        android:title="Blue"
        app:showAsAction="ifRoom|withText"
        android:orderInCategory="3"
        />
    <item
        android:id="@+id/maroon"
        android:title="Maroon"
        app:showAsAction="ifRoom|withText"
        android:orderInCategory="4"
        />
    <item
        android:id="@+id/orange"
        android:title="Orange"
        app:showAsAction="never|withText"
        android:orderInCategory="5"
        />
    <item
        android:id="@+id/purple"
        android:title="Purple"
        app:showAsAction="withText|withText"
        android:orderInCategory="6"
        />
    <item
        android:id="@+id/black"
        android:title="Black"
        app:showAsAction="withText|collapseActionView"
        android:orderInCategory="7"
        />
</menu>
-----------
manifeast
  <?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.pankaj.menu51">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
  
