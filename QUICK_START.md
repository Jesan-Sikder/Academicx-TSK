# Quick Start Guide - Academicx TSK

## ⚡ Get Started in 5 Minutes

### Step 1: Prerequisites
- [ ] Install Android Studio Hedgehog or later
- [ ] Install JDK 17 or later
- [ ] Have an Android device or emulator ready (API 26+)

### Step 2: Clone & Open
```bash
git clone https://github.com/hr628/academicx-tsk.git
cd academicx-tsk
```
Open the project in Android Studio and wait for Gradle sync.

### Step 3: Configure API Key (For AI Features)
1. Get FREE API key: https://makersuite.google.com/app/apikey
2. Copy `local.properties.template` to `local.properties`
3. Add your key:
```properties
GEMINI_API_KEY=your_actual_key_here
```

### Step 4: Run!
- Click the green ▶️ Run button in Android Studio
- Or press `Shift + F10`
- Choose your device/emulator
- Wait for app to build and launch

### Step 5: Start Using
1. **Add a Task:** Tap the + button
2. **Fill Details:** Title, course, type, date, time
3. **Save:** Task appears in your list
4. **Get Notifications:** Auto-scheduled for 1 day before & on due date
5. **Try AI:** Tap the robot icon for study assistance

---

## 🎯 Common Tasks

### Add Your First Task
```
Title: Midterm Exam
Course: Computer Science 101
Type: Midterm
Due Date: [Select from picker]
Due Time: 14:00
Notes: Chapters 1-5
```

### Use AI Assistant
Quick suggestions:
- "What should I prioritize?"
- "Help me plan my week"
- "Give me study tips"

Or tap "Analyze Tasks" button for instant analysis.

### Mark Tasks Complete
- Tap the circle icon on any task card
- It moves to "Completed" section
- Notifications auto-cancel

### Edit/Delete Tasks
- Tap any task card to open editor
- Tap trash icon to delete
- Changes save automatically

---

## 🔥 Pro Tips

1. **Custom Task Types:** Select "Custom" from dropdown, name it anything
2. **Batch Add:** Add multiple tasks quickly - navigation is instant
3. **Morning Reminders:** All notifications come at 9 AM by default
4. **Offline Mode:** Everything works without internet (except AI)
5. **Dark Mode:** Always on for better battery life

---

## ⚠️ Troubleshooting

### "Build failed"
- Ensure JDK 17 is selected
- Run `File → Invalidate Caches → Restart`
- Check `local.properties` exists

### "API key invalid"
- Verify key from Google AI Studio
- Check no extra spaces in `local.properties`
- API key should be plain text, no quotes needed

### "Notifications not showing"
- Grant notification permission in Settings
- Check Do Not Disturb is off
- Ensure battery optimization is disabled for app

### "AI not responding"
- Verify API key is set correctly
- Check internet connection
- API has rate limits (60 requests/minute for free tier)

---

## 📱 System Requirements

**Minimum:**
- Android 8.0 (API 26)
- 50 MB storage
- Internet for AI (optional)

**Recommended:**
- Android 13+ (API 33)
- 100 MB storage
- Active internet connection

---

## 🎨 Customization

### Change Theme Colors
Edit `app/src/main/java/com/jesan/tsk/ui/theme/Color.kt`:
```kotlin
val Indigo = Color(0xFF6366F1)  // Change to your color
```

### Add More Task Types
Edit `app/src/main/java/com/jesan/tsk/domain/model/TaskType.kt`:
```kotlin
HOMEWORK("Homework", "#3B82F6"),
```

### Change Notification Times
Edit `app/src/main/java/com/jesan/tsk/utils/Constants.kt`:
```kotlin
const val DEFAULT_NOTIFICATION_HOUR = 8  // Change from 9 to 8
```

---

## 🚀 Advanced Setup

### Enable Cloud Sync (Optional)

1. **Create Firebase Project:**
   - Go to https://console.firebase.google.com
   - Create project "Academicx TSK"

2. **Add Android App:**
   - Package: `com.jesan.tsk`
   - Download `google-services.json`
   - Place in `app/` folder

3. **Enable Services:**
   - Authentication → Google Sign-In
   - Firestore Database → Create database

4. **Update Build Config:**
   In `app/build.gradle.kts`, change:
   ```kotlin
   id("com.google.gms.google-services") apply false
   ```
   To:
   ```kotlin
   id("com.google.gms.google-services")
   ```

5. **Sync & Rebuild**

---

## 📊 What to Test

- [ ] Add task with all fields
- [ ] Edit existing task
- [ ] Delete task
- [ ] Mark complete/incomplete
- [ ] Date picker works
- [ ] Time picker works
- [ ] Notifications appear
- [ ] AI responds (with API key)
- [ ] App persists data after closing
- [ ] Navigation works smoothly

---

## 💡 Features Overview

| Feature | Status | Requirement |
|---------|--------|-------------|
| Task Management | ✅ Ready | None |
| Notifications | ✅ Ready | Permission |
| Dark Theme | ✅ Always On | None |
| AI Assistant | 🔑 Needs Key | Gemini API |
| Cloud Sync | ☁️ Optional | Firebase |
| Offline Mode | ✅ Ready | None |

---

## 🆘 Need Help?

1. Check `README.md` for detailed docs
2. Review `IMPLEMENTATION_SUMMARY.md` for architecture
3. Read inline code comments
4. Open GitHub issue for bugs

---

## ✨ You're All Set!

The app is ready to use. Start managing your academic tasks efficiently! 🎓

**Happy Studying! 📚**
