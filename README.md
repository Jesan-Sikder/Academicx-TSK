# Academicx TSK - Premium Academic Task & Reminder App

<div align="center">

**A complete production-ready Android app for university students to manage academic tasks with AI assistant integration.**

[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://www.android.com/)
[![Language](https://img.shields.io/badge/Language-Kotlin-blue.svg)](https://kotlinlang.org/)
[![API](https://img.shields.io/badge/API-26%2B-brightgreen.svg)](https://android-arsenal.com/api?level=26)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

</div>

## 📱 About

Academicx TSK is a premium dark-themed Android application designed specifically for university students to efficiently manage their academic tasks, assignments, quizzes, and exams. With intelligent AI assistance powered by Google's Gemini AI, students can get personalized study recommendations and time management tips.

## ✨ Features

### Core Functionality
- ✅ **Complete Task Management** - Create, read, update, and delete tasks
- 📅 **Smart Scheduling** - Set due dates and times for all academic tasks
- 🔔 **Intelligent Notifications** - Automated reminders (1 day before & on due date at 9 AM)
- ✅ **Task Completion Tracking** - Mark tasks as complete/incomplete
- 📊 **Task Organization** - View tasks grouped by "Upcoming" and "Completed"

### Task Types
- Quiz 1, Quiz 2, Quiz 3, Extra Quiz
- Assignment
- Midterm Exam
- Final Exam
- Project
- Presentation
- Custom task types (create your own!)

### AI Assistant
- 🤖 **Gemini AI Integration** - Chat with an AI study assistant
- 💡 **Smart Suggestions** - Get priority recommendations based on your tasks
- 📚 **Study Tips** - Receive personalized study advice
- ⏰ **Time Management** - AI analyzes your workload and helps you plan

### User Interface
- 🌙 **Dark Mode by Default** - Premium dark theme for comfortable viewing
- 🎨 **Material 3 Design** - Modern, beautiful UI with smooth animations
- 📱 **Intuitive Navigation** - Easy-to-use interface with floating action buttons
- 🎯 **Urgency Indicators** - Color-coded badges for "Tomorrow", "This week", etc.

### Optional Features
- ☁️ **Cloud Sync** - Firebase integration for backing up tasks (optional)
- 👤 **Google Sign-In** - Optional cloud backup via Google account
- 🔄 **Offline First** - App works 100% offline without any account

## 🏗️ Technical Stack

### Core Technologies
- **Language:** Kotlin
- **UI Framework:** Jetpack Compose (Material 3)
- **Architecture:** MVVM + Clean Architecture
- **Database:** Room (local storage)
- **Dependency Injection:** Hilt
- **Async Operations:** Kotlin Coroutines & Flow
- **Navigation:** Jetpack Compose Navigation

### Backend & Cloud (Optional)
- **AI:** Google Gemini AI API
- **Authentication:** Firebase Authentication (Google Sign-In)
- **Cloud Storage:** Firebase Firestore
- **Notifications:** WorkManager for scheduled reminders

## 🚀 Getting Started

### Prerequisites
- Android Studio Hedgehog (2023.1.1) or later
- JDK 17 or later
- Android SDK API 34
- Android device or emulator with API 26+ (Android 8.0+)

### Installation & Setup

#### 1. Clone the Repository
```bash
git clone https://github.com/hr628/academicx-tsk.git
cd academicx-tsk
```

#### 2. Configure Gemini AI API Key
1. Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Copy `local.properties.template` to `local.properties`
3. Add your API key:
```properties
GEMINI_API_KEY=your_actual_api_key_here
```

#### 3. Firebase Setup (Optional - for cloud sync)
If you want to enable cloud backup features:

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create a new project named "Academicx TSK"
3. Add an Android app with package name: `com.jesan.tsk`
4. Download `google-services.json`
5. Place it in the `app/` directory
6. Enable:
   - **Authentication** → Google Sign-In provider
   - **Firestore Database** → Start in production mode

7. Uncomment the Firebase plugin in `app/build.gradle.kts`:
```kotlin
// Change this line:
id("com.google.gms.google-services") apply false

// To this:
id("com.google.gms.google-services")
```

#### 4. Build & Run
1. Open the project in Android Studio
2. Let Gradle sync complete
3. Connect an Android device or start an emulator
4. Click Run or press Shift + F10

#### 5. Generate APK
```bash
# Debug APK
./gradlew assembleDebug

# Release APK (unsigned)
./gradlew assembleRelease
```

APK will be generated in: `app/build/outputs/apk/`

## 📐 Architecture

The app follows **Clean Architecture** principles with **MVVM** pattern:

```
app/
├── data/                      # Data Layer
│   ├── local/                 # Local database (Room)
│   │   ├── database/          # Database & DAOs
│   │   └── entity/            # Room entities
│   ├── remote/                # Remote data sources (Firebase)
│   └── repository/            # Repository implementations
├── domain/                    # Domain Layer
│   └── model/                 # Business models
├── ui/                        # Presentation Layer
│   ├── screens/               # App screens
│   │   ├── home/             # Home screen
│   │   ├── addtask/          # Add task screen
│   │   ├── edittask/         # Edit task screen
│   │   ├── ai/               # AI assistant screen
│   │   └── settings/         # Settings screen
│   ├── components/            # Reusable UI components
│   ├── theme/                 # Theme configuration
│   └── navigation/            # Navigation graph
├── notifications/             # Notification system
├── utils/                     # Utility classes
└── di/                        # Dependency injection modules
```

## 🎨 Design

### Color Scheme (Dark Theme)
- **Primary:** Indigo (#6366F1)
- **Secondary:** Purple (#8B5CF6)
- **Background:** Dark Blue (#0F172A)
- **Surface:** Lighter Dark (#1E293B)
- **Error:** Red (#EF4444)

### Task Type Colors
- **Quiz:** Blue (#3B82F6)
- **Assignment:** Orange (#F97316)
- **Exam:** Red (#EF4444)
- **Project:** Purple (#8B5CF6)
- **Presentation:** Green (#10B981)
- **Custom:** Indigo (#6366F1)

## 🔔 Notification System

Tasks automatically schedule two notifications:
1. **1 day before** due date at 9:00 AM
2. **On due date** at 9:00 AM

Notifications are:
- Automatically scheduled when creating/updating tasks
- Cancelled when tasks are marked complete or deleted
- Persist even after app restart (using WorkManager)

## 🤖 AI Assistant Usage

The AI assistant can help with:
- **Task Analysis:** "What should I prioritize?"
- **Planning:** "Help me plan my week"
- **Study Tips:** "Give me study tips"
- **Custom Questions:** Ask anything about your academic workload

The AI uses your actual tasks as context to provide personalized advice.

## 📱 Usage

### Adding a Task
1. Tap the **+** floating action button
2. Fill in task details:
   - Task title
   - Course name
   - Task type (or create custom)
   - Due date and time
   - Optional notes
3. Tap "Add Task"

### Managing Tasks
- **Complete:** Tap the circle icon on any task card
- **Edit:** Tap on a task card to edit details
- **Delete:** Open task → Tap trash icon → Confirm

### Using AI Assistant
1. Tap the **AI** floating action button (robot icon)
2. Use quick buttons or type your question
3. Get personalized recommendations

## 🔒 Permissions

The app requests these permissions:
- **INTERNET** - For AI features and optional cloud sync
- **POST_NOTIFICATIONS** - For task reminder notifications
- **SCHEDULE_EXACT_ALARM** - For precise notification timing

## 🛠️ Development

### Running Tests
```bash
# Unit tests
./gradlew test

# Instrumented tests
./gradlew connectedAndroidTest
```

### Code Style
The project follows official Kotlin coding conventions and uses Material 3 design guidelines.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Contact: [Your Contact Info]

## 🙏 Acknowledgments

- **Google Gemini AI** for intelligent assistance
- **Firebase** for backend services
- **Material Design** for beautiful UI components
- **Android Jetpack** for modern Android development

---

<div align="center">

**Made with ❤️ for students by students**

</div>
