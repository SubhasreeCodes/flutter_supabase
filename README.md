# Flutter Supabase Authentication

This is a basic Flutter project integrated with Supabase for user authentication. It includes the following features:

- **User Registration**: Allow users to create a new account with email and password.
- **User Login**: Allows users to log in with their registered email and password.
- **User Logout**: Allows users to log out of the application.

## Prerequisites

Before running this project, make sure you have the following installed:

- [Flutter](https://flutter.dev/docs/get-started/install)
- [Supabase Account](https://supabase.io/)
- [Supabase Project](https://app.supabase.io/) set up

## Setup

### Step 1: Create a Supabase Project

1. Go to [Supabase](https://app.supabase.io/) and create a new project.
2. From the Supabase dashboard, navigate to **Authentication > Settings** and enable **Email** for authentication.
3. Copy the `URL` and `anon key` from your project's API settings (located under **Project Settings > API**).

### Step 2: Install Dependencies

1. Create a new Flutter project or use an existing one.
2. Open `pubspec.yaml` and add the following dependencies:

```yaml
dependencies:
  flutter:
    sdk: flutter
  supabase_flutter: ^0.2.8
  flutter_secure_storage: ^5.0.2
  fluttertoast: ^8.0.9
```

3. Run the following command to install the dependencies:

```bash
flutter pub get
```

### Step 3: Initialize Supabase

1. In your Flutter project, open `lib/main.dart` and initialize Supabase as follows:

```dart
import 'package:flutter/material.dart';
import 'package:supabase_flutter/supabase_flutter.dart';
import 'screens/LoginScreen.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Supabase.initialize(
    url: 'your-supabase-url', // Replace with your Supabase URL
    anonKey: 'your-supabase-anon-key', // Replace with your Supabase anon key
  );
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Supabase Auth',
      home: LoginScreen(title: 'Login'),
    );
  }
}
```

### Step 4: Create Screens for Login, Registration, and Home

- **LoginScreen.dart**: Contains user login form.
- **RegisterScreen.dart**: Contains user registration form.
- **HomeScreen.dart**: Displays after successful login.

### Step 5: Add Authentication Logic

Ensure you have implemented the registration, login, and logout logic as follows:

- **Registration**: Allows users to sign up with their email and password.
- **Login**: Allows users to sign in with their email and password.
- **Logout**: Logs the user out and redirects to the login screen.

For implementation details, check the `RegisterScreen.dart` and `LoginScreen.dart` in the `lib/screens/` directory.

## Running the Project

1. Run the project on your emulator or device:

```bash
flutter run
```

2. You should be able to:
    - Register a new user by entering an email and password.
    - Log in using the credentials you registered with.
    - Log out and be redirected to the login screen.

## Troubleshooting

- **Error: 'RegisterScreen' is imported from both...**: This happens due to double imports in your code. Ensure your import paths are correct.

- **Authentication not working**: Ensure you have properly initialized Supabase in your `main.dart` file, and double-check the Supabase URL and anon key.

## License

This project is open-source and available under the [MIT License](LICENSE).
```

