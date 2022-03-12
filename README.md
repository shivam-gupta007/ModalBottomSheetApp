# How to create Modal Bottom Sheet Like Instagram?

### This repository focuses on making Modal Bottom Sheet Like Instagram in android with kotlin:

![IMG_20220311_233011](https://user-images.githubusercontent.com/83108424/158026669-21682898-d3e3-4919-8b1e-c7789b4400d6.jpg)

#### 1. Create an empty project in android studio

#### 2. Create an empty fragment named as ``` ModalBottomSheet ``` in that project

#### 3. Add this code in ``` ModalBottomSheet.kt ``` file (Fragment kotlin file)

```KOTLIN
package com.example.bottomSheetApp

import android.os.Bundle
import android.view.Gravity
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import android.widget.TextView
import android.widget.Toast
import com.google.android.material.bottomsheet.BottomSheetDialogFragment


    class ModalBottomSheet : BottomSheetDialogFragment() {

    override fun onCreateView(
        inflater: LayoutInflater, container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {

        val view = inflater.inflate(R.layout.fragment_modal_bottom_sheet, container, false)

        val postLayout = view.findViewById<TextView>(R.id.postLayout);
        val reelLayout = view.findViewById<TextView>(R.id.reelLayout);
        val storyLayout = view.findViewById<TextView>(R.id.storyLayout);
        val storyHighLightLayout = view.findViewById<TextView>(R.id.storyHighLightLayout);
        val liveLayout = view.findViewById<TextView>(R.id.liveLayout);
        val guideLayout = view.findViewById<TextView>(R.id.guideLayout);

        postLayout.setOnClickListener {
            showToast("Post")
        }

        reelLayout.setOnClickListener {
            showToast("Reels")
        }

        storyLayout.setOnClickListener {
            showToast("Story")
        }

        storyHighLightLayout.setOnClickListener {
            showToast("Story HighLight")
        }

        liveLayout.setOnClickListener {
            showToast("Live")
        }

        guideLayout.setOnClickListener {
            showToast("Guide")
        }

        return view;
    }

    private fun showToast(msg: String) {
        val toast = Toast.makeText(requireContext(), msg, Toast.LENGTH_SHORT)
        toast.setGravity(Gravity.CENTER, 0, 250)
        toast.show()
    }

    companion object {
        const val TAG = "ModalBottomSheet"
    }
}

```

#### 4. Add this code in ``` fragment_modal_bottom_sheet.xml ``` (Fragment XML File)

```XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/bottom_sheet_container"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/gray"
    android:orientation="vertical"
    android:paddingBottom="65dp">

    <View
        android:id="@+id/line1"
        android:layout_width="50dp"
        android:layout_height="3dp"
        android:layout_gravity="center"
        android:layout_marginTop="15dp"
        android:background="#DCDCDC" />

    <TextView
        android:id="@+id/title_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="15dp"
        android:text="@string/create"
        android:textAlignment="center"
        android:textColor="@color/white"
        android:textSize="20sp"
        android:textStyle="bold" />

    <View
        android:id="@+id/line2"
        android:layout_width="match_parent"
        android:layout_height="1dp"
        android:layout_marginTop="15dp"
        android:background="#6A6A6A" />

    <TextView
        android:id="@+id/postLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginLeft="15dp"
        android:layout_marginTop="25dp"
        android:layout_marginRight="15dp"
        android:padding="10dp"
        android:drawableStart="@drawable/ic_grid"
        android:drawablePadding="15dp"
        android:text="@string/post"
        android:textColor="@color/white"
        android:textSize="18sp"
        app:drawableTint="@color/white" />

    <TextView
        android:id="@+id/reelLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="10dp"
        android:layout_marginLeft="15dp"
        android:layout_marginTop="10dp"
        android:layout_marginRight="15dp"
        android:drawableStart="@drawable/ic_reels"
        android:drawablePadding="15dp"
        android:text="@string/reels"
        android:textColor="@color/white"
        android:textSize="18sp"
        app:drawableTint="@color/white" />


    <TextView
        android:id="@+id/storyLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="10dp"
        android:layout_marginLeft="15dp"
        android:layout_marginTop="10dp"
        android:layout_marginRight="15dp"
        android:drawableStart="@drawable/ic_story"
        android:drawablePadding="15dp"
        android:text="@string/story"
        android:textColor="@color/white"
        android:textSize="18sp"
        app:drawableTint="@color/white" />

    <TextView
        android:id="@+id/storyHighLightLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="10dp"
        android:layout_marginLeft="15dp"
        android:layout_marginTop="10dp"
        android:layout_marginRight="15dp"
        android:drawableStart="@drawable/ic_story_highlight"
        android:drawablePadding="15dp"
        android:text="@string/story_highlight"
        android:textColor="@color/white"
        android:textSize="18sp" />

    <TextView
        android:id="@+id/liveLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="10dp"
        android:layout_marginLeft="15dp"
        android:layout_marginTop="10dp"
        android:layout_marginRight="15dp"
        android:drawableStart="@drawable/ic_live"
        android:drawablePadding="15dp"
        android:text="@string/live"
        android:textColor="@color/white"
        android:textSize="18sp"
        app:drawableTint="@color/white" />

    <TextView
        android:id="@+id/guideLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="10dp"
        android:layout_marginLeft="15dp"
        android:layout_marginTop="10dp"
        android:layout_marginRight="15dp"
        android:layout_marginBottom="20dp"
        android:drawableStart="@drawable/ic_guide"
        android:drawablePadding="15dp"
        android:text="@string/guide"
        android:textColor="@color/white"
        android:textSize="18sp"
        app:drawableTint="@color/white" />

</LinearLayout>

```

#### 5. Add this code in ``` MainActivity.kt ```

```KOTLIN
package com.example.bottomSheetApp

import android.os.Bundle
import android.widget.Button
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val showButton = findViewById<Button>(R.id.show_button)

        showButton.setOnClickListener {
            val modalBottomSheet = ModalBottomSheet()
            modalBottomSheet.show(supportFragmentManager, ModalBottomSheet.TAG)
        }

    }
}

````

#### 6. Add this code in ``` activity_main.xml ```

```XML
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_gravity="center"
    android:background="@color/white"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/show_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Open Bottom Sheet"
        android:backgroundTint="@color/black"
        android:textColor="@color/white"
        android:paddingTop="15dp"
        android:paddingBottom="15dp"
        android:paddingRight="20dp"
        android:paddingLeft="20dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />


</androidx.constraintlayout.widget.ConstraintLayout>
```
