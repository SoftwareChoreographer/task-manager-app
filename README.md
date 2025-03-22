
# Task Manager App 📱✅

A simple task management Android app built with Jetpack Compose to display a "Task Completed" screen. This app is part of a task management system where users can see a congratulatory message when all tasks are completed. 🎉

## Features ✨

- **Task Completed Screen:** Displays an image and two text messages when all tasks are completed. 🏁
- **Jetpack Compose:** UI is built using Jetpack Compose, the modern toolkit for building Android UIs. 🖥️
- **Custom Theming:** Uses `Material3` theming to style the app. 🎨

## Prerequisites 🛠️

To run this project, ensure you have the following:

- Android Studio (latest version recommended) 📲
- An Android device or emulator for running the app 🖥️
- Kotlin 1.5 or higher 🦸‍♂️
- Android SDK installed 🛠️

## Project Setup 🗂️

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/softwarechoreographer/task-manager-app.git
   ```

2. Open the project in Android Studio. 🏙️

3. Sync the project with Gradle files by clicking on **"Sync Now"** in the top right corner.

4. Ensure your Android emulator is running or connect a physical device. 📱

5. Run the app by clicking the **Run** button (green triangle) in Android Studio. ▶️

## Code Overview 💻

### MainActivity 🏠

The `MainActivity` serves as the entry point for the app. It sets the content view with a `TaskManagerAppTheme` and displays the `TaskCompletedScreen`.

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            TaskManagerAppTheme {
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    TaskCompletedScreen()
                }
            }
        }
    }
}
```

### TaskCompletedScreen ✅

The `TaskCompletedScreen` is a Composable function that displays a column with an image and two text elements. The text displays a message to congratulate the user for completing all tasks. 🎉

```kotlin
@Composable
fun TaskCompletedScreen() {
    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Image(
            painter = painterResource(R.drawable.ic_task_completed),
            contentDescription = null
        )
        Text(
            text = stringResource(R.string.all_task_completed),
            modifier = Modifier.padding(top = 24.dp, bottom = 8.dp),
            fontWeight = FontWeight.Bold,
            fontSize = 24.sp
        )
        Text(
            text = stringResource(R.string.nice_work),
            fontSize = 16.sp
        )
    }
}
```

### TaskCompletedPreview 👀

This is a preview of the `TaskCompletedScreen` to see how it looks during development in Android Studio.

```kotlin
@Preview(showBackground = true)
@Composable
fun TaskCompletedPreview() {
    TaskManagerAppTheme {
        TaskCompletedScreen()
    }
}
```

## Assets 🖼️

- `ic_task_completed`: This image represents the completion of tasks. It can be found in the `res/drawable` directory. 🏆

## Customizations 🛠️

- Modify the text strings in the `strings.xml` file located under `res/values/strings.xml` to change the messages displayed on the screen. 📝
- Replace the `ic_task_completed` image in the `res/drawable` folder with your custom image if needed. 🖼️

## License 📜

This project is open source and available under the [MIT License](LICENSE).
