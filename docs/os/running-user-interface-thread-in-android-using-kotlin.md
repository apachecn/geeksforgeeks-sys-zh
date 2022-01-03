# 使用 Kotlin 在安卓中运行用户界面线程

> 原文:[https://www . geesforgeks . org/running-user-interface-thread-in-Android-using-kot Lin/](https://www.geeksforgeeks.org/running-user-interface-thread-in-android-using-kotlin/)

**Android 中的用户界面线程**或 UI-Thread 是负责隐式或显式更新应用程序布局元素的线程元素。这意味着，要在应用程序布局(即应用程序前端)中更新元素或更改其属性，可以使用用户界面线程。

**实现 UI Thread:**
比如一个线程动作启动，开发者想针对线程元素更新前端元素，可以使用**runnonithread {…}**功能。
下面是使用 UI 线程的应用示例。

**<u>示例应用，其中文本视图中的文本每秒都在更改</u>**

最初，应用程序将显示一条欢迎消息，一旦点击**开始**按钮，它将每秒交替显示 2 条消息，“爱 gfg”和“不爱 gfg”。

**进场:**
**第一步:**在 **activity_main.xml** 中添加以下代码。在这里，添加一个文本视图和一个按钮到我们的主活动布局。

## 超文本标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/tv1"
        android:layout_width="210sp"
        android:layout_height="100sp"
        android:layout_centerInParent="true"
        android:gravity="center"
        android:textSize="50sp"
        android:text="Welcome"
        />

    <Button
        android:id="@+id/btnStart"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Start"
        android:layout_below="@id/tv1"
        android:layout_centerHorizontal="true"
        />

</RelativeLayout>
```

**第二步:**在 MainActivity 中添加下面的代码。这里 OnClickListener 是用按钮添加的。所以每当用户点击按钮时就会调用它。在侦听器中，在主线程中创建了一个无限循环，使用用户界面线程，文本每秒钟都在改变。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?)
    {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Assigning Layout elements
        val tv = findViewById<TextView>(R.id.tv1)
        val btn = findViewById<Button>(R.id.btnStart)
        val msg1 = "love gfg" val msg2 = "not gfg"

        // Button onClick action
        btn.setOnClickListener
        {
            // Declaring Main Thread
            Thread(Runnable {
                while (true) {
                    // Updating Text View at current
                    // iteration
                    runOnUiThread{ tv.text = msg1 }

                    // Thread sleep for 1 sec
                    Thread.sleep(1000)
                    // Updating Text View at current
                    // iteration
                    runOnUiThread{ tv.text = msg2 }

                    // Thread sleep for 1 sec
                    Thread.sleep(1000)
                }
            }).start()
        }
    }
}
```

<video class="wp-video-shortcode" id="video-439107-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200614002704/InShot_20200614_0012453282.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200614002704/InShot_20200614_0012453282.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200614002704/InShot_20200614_0012453282.mp4)</video>

***注意:****While 循环**只能在线程内部声明。如果在 while 循环中声明了一个 Thread，程序将无法工作并崩溃。*

**<u>示例定时器 App</u>**
从以上代码的基本概念，可以设计出一款定时器 App。下面是相同的代码:

**进场:**
**第一步:**在 MainActivity 布局中添加以下代码。这里添加了按钮、edittext 和 textview。按钮用于启动计时器，edittext 用于接收用户输入，textview 用于显示剩余时间。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/btnStart"
        android:layout_width="100sp"
        android:layout_height="50sp"
        android:layout_centerInParent="true"
        android:text="Start"
        />

    <EditText
        android:id="@+id/et1"
        android:layout_width="100sp"
        android:layout_height="100sp"
        android:layout_centerHorizontal="true"
        android:layout_above="@id/btnStart"
        android:textSize="50sp"
        android:inputType="number"
        android:gravity="center"
        android:background="@color/colorPrimary"
        android:textColor="@color/colorAccent"
        />

    <TextView
        android:id="@+id/tv1"
        android:layout_width="100sp"
        android:layout_height="100sp"
        android:layout_centerHorizontal="true"
        android:layout_below="@id/btnStart"
        android:gravity="center"
        android:textSize="50sp"
        android:background="@color/colorPrimaryDark"
        android:textColor="@color/colorAccent"
        />

</RelativeLayout>
```

**第二步:**在 MainActivity 类中添加下面的代码。这里我们用按钮添加 **onClickListener** 。点击按钮时，**运行无信息读取**功能显示剩余时间。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?)
    {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Assigning Layout elements
        val et = findViewById<EditText>(R.id.et1)
        val btn = findViewById<Button>(R.id.btnStart)
        val tv = findViewById<TextView>(R.id.tv1)

              // Button onClick action
        btn.setOnClickListener{
            // Converting Edit Text input to String
            val stringTime= (et.text).toString()
            // Converting stringTime to Integer
            val intTime= Integer.parseInt(stringTime)
            // Declaring Main Thread
             Thread(Runnable {
                  // For loop Decrement
                  for (i in intTime downTo 0) {
                       // Updating Text View at
                       // current iteration
                        runOnUiThread{
                            tv.text = i.toString()
                         }

                   // Thread sleep for 1 sec
                        Thread.sleep(1000)
                          }
                      }).start()
        }
    }
}
```

<video class="wp-video-shortcode" id="video-439107-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200614002533/InShot_20200614_0010422392.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200614002533/InShot_20200614_0010422392.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200614002533/InShot_20200614_0010422392.mp4)</video>