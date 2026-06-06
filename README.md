# 🌌 Monolith — Unified Enterprise Collaborative Task & Calendar Suite

[![Kotlin](https://img.shields.io/badge/Kotlin-1.9.22-purple.svg?style=flat&logo=kotlin)](https://kotlinlang.org)
[![Compose](https://img.shields.io/badge/Jetpack_Compose-M3-green.svg?style=flat&logo=jetpackcompose)](https://developer.android.com/jetpack/compose)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84.svg?style=flat&logo=android)](https://developer.android.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Monolith** is a unified collaborative task manager and calendar suite for Android, designed with a premium, immersive **electric-blue glassmorphic visual system**. Crafted strictly using **Jetpack Compose (Material 3)**, modern **Clean Architecture/MVVM**, and integrated with server-side **Gemini AI**, Monolith elevates workspace productivity into a high-fidelity visual experience.

---

## 🎨 Visual Identity & Premium Styling

Monolith departs from generic, uninspired administrative layouts, replacing them with a gorgeous **electric-blue neon glassmorphic aesthetic**.

Features of the visual design system:
* **True Volumetric Glassmorphism**: Translucent card backgrounds layered with specular diagonal light reflection gradients, mimicking polished acrylic refraction.
* **Tactile Interactions**: All primary layout actions (like the premium Excel Compile button) include spring-interpolated scale responses on touch.
* **Ambient Glow Breathing**: Infinite repeatable pulse and sweep transitions illuminate borders with subtle, eye-safe cyan and violet light leaks.
* **Material Symbols Integration**: High-density use of custom-themed iconic actions of both filled status and outlined secondary styles.

---

## 🚀 Key Feature Modules

### 1. 📅 Interactive Task and Calendar Dashboard
* **Dynamic Agenda View**: Comprehensive multi-tab overview tracking calendar deadlines, presence states, and milestone histories.
* **Responsive Category Filtering**: Organize tasks instantly by work, personal, critical meetings, or custom priorities.

### 2. 📋 Enterprise Kanban Board (`EnterpriseKanban.kt`)
* **Flexible Workflows**: Interactive task statuses organized in distinct progression lanes.
* **Tactile Tracking**: Check subtasks, edit descriptions, or transition states on a responsive canvas.

### 3. 🧠 Smart Subtasks with Server-Side Gemini AI
* **Checklist Suggestions**: Don't waste time planning. Integrated with the Gemini API to automatically dissect arbitrary, loose task descriptions into targeted, multi-step subtask checklists instantly.
* **Offline Compatibility Fallbacks**: Gracefully switches to localized procedural parsing if API keys or connections are absent.

### 4. 🔗 Background Workspace Sync Service (`WorkspaceSyncService.kt`)
* **Real-time Live Sync**: A background polling and notification service running continuously to fetch shared team coordinates and flag active workspace updates.
* **Presence Indicators**: Visual confirmation of active team access, verifying secure and responsive administrative sync.

### 5. 🔔 Volumetric Floating Overlay Notification (`OverlayService.kt`)
* **Floating Heads-Up Display**: A persistent foreground window presenting newly assigned tasks using rich glassmorphic frames.
* **Real-time Subtask Expansion**: Expand and inspect corresponding task sublists directly from the floating system overlay, built with smooth layout transition builders.

### 6. 📊 Enterprise Analytics Dashboard (`EnterpriseAnalytics.kt`)
* **Activity & Productivity Charts**: Track milestone histories, completed task distributions, and personal output velocities over time.
* **Data Transparency Log**: Audit trailing synchronization histories in a dedicated, gorgeous console.

### 7. 🛡️ Advanced Admin Controls & Excel Compiler (`EnterpriseAdmin.kt`)
* **Secure Access Safeguards**: Locking mechanisms shielding enterprise configurations.
* **Elite Glass Excel Compiler**: Compile and download complete, cleanly structured Excel administrative task spreadsheets directly on the device!

---

## 🛠️ Architecture and Stack

Monolith utilizes a modern, robust, and completely offline-first Android codebase:

| Layer | Technology | Purpose |
|---|---|---|
| **UI Framework** | **Jetpack Compose (M3)** | Single-activity responsive screens, canonical multi-pane support, dynamic color palettes, and heavy system theme. |
| **Architectural Pattern** | **MVVM (Model-View-ViewModel)** | Centralized system state using unidirectional flow streams (`StateFlow`/`SharedFlow`). |
| **Local Database** | **Room Persistence Library** | Full offline storage backing all calendars, active sessions, subtasks, and logs with localized SQLite tables. |
| **Network & AI** | **Gemini REST API / Retrofit** | Direct client-to-engine API operations facilitating automated checklist synthesis. |
| **Background Processing** | **Android Services & Coroutines** | Infinite background worker pipelines tracking remote task assignments. |
| **Design Extras** | **Android Window Insets & Edge-to-Edge** | Full support for gesture navigation, system bar color matching, and variable display cutouts. |

---

## 📂 Codebase File Tour

```plaintext
com.example
├── MainActivity.kt                      # Application Controller & Core Navigation Host
├── data
│   ├── Models.kt                        # Data schemas (Task, Member, Log, Subtask)
│   ├── AppDaos.kt                       # Room database queries and operations
│   ├── AppDatabase.kt                   # Room SQLite database implementation builder
│   └── AppRepository.kt                 # Integrated offline-first data manager
├── network
│   └── GeminiService.kt                 # Integrated REST APIs for AI and subtask predictions
└── ui
    ├── EnterpriseAdmin.kt               # Administrative locks and interactive Excel exporter
    ├── EnterpriseAnalytics.kt           # Rich chart interfaces and logging consoles
    ├── EnterpriseKanban.kt              # Project layout board and column views
    ├── MonolithViewModel.kt             # Shared architecture view model and business engine
    ├── NotificationCenterDialogView.kt  # Dedicated system status menu interactions
    ├── OverlayService.kt                # Foreground overlay controller with expanding subtask previews
    └── theme
        ├── Theme.kt                     # Modern Material 3 electric dynamic palette configuration
        └── Color.kt                     # Volumetric gradients, glowing space slate declarations
```

---

## 🚦 Getting Started

### Prerequisites
* **Android Studio Iguana** (or newer)
* **Android SDK 34** (targetSdkVersion)
* **Gradle 8.2+**
* An Android Device running **Android 8.0 (API 26)** or higher (needed for the system overlay service).

### Real-Time Secrets Configuration
Secure credentials (such as your **Gemini API Key**) are isolated using the Android Secrets Gradle Plugin.
1. Create a `.env` file in your root workspace:
   ```env
   GEMINI_API_KEY=your_actual_api_key_here
   ```
2. The compiler will automatically bind this coordinate into your `BuildConfig.GEMINI_API_KEY` at build-time. No secrets are ever hardcoded.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/monolith-android.git
   ```
2. Open the project in Android Studio.
3. Sync Project with Gradle Files.
4. Hit **Run** (`Shift + F10`) to deploy to your emulator or physical hardware.

---

## 🔒 Permissions Used
To serve collaborative notifications and headups alerts flawlessly, Monolith employs:
* `SYSTEM_ALERT_WINDOW`: Drives the custom glassmorphic task overlay window.
* `POST_NOTIFICATIONS`: Registers immediate action cards in the Android system shade.
* `FOREGROUND_SERVICE`: Runs the background notification and sync worker.
* `INTERNET`: Bridges workspace sharing and Gemini AI query pipelines.

---

## 🏆 Project Achievements
* **100% Jetpack Compose implementation** — absolutely zero legacy Android XML layouts.
* **Rigorous edge-to-edge UI safety** respecting system navigation rails in portrait, landscape, and multi-window configurations.
* **Low memory footprint** background synchronization leveraging efficient asynchronous Kotlin Flows.
