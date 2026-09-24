# Autoverse Spares — B2B Auto Parts App for Garages (Android)

> **Note:** This is a production app I work on professionally. The source code is proprietary and confidential, so this repository contains **only a project overview** — no source code, credentials, or internal details.

<!-- Add Play Store link here if the app is public -->
<!-- [Get it on Google Play](https://play.google.com/store/apps/details?id=...) -->

## Overview

Autoverse Spares is a B2B Android app for independent car garages and workshops in India. Garages use it to find the right spare parts for a customer's vehicle, order them with fast delivery, and run day-to-day workshop operations — job cards, customer quotations, payments and staff — from a single app.

- In production since 2022, shipped through 50+ releases
- ~1,100 Kotlin source files across 40+ feature modules

## Key Features

**Parts discovery & ordering**
- Vehicle-based part lookup: pick make → model → variant → year, or enter the registration number
- Fast search with suggestions, filters (brand, category, vehicle) and sorting
- Camera-based scanning with on-device text recognition (ML Kit) to capture part/vehicle details
- Browse by brand and category, plus curated service kits and clutch kits
- Cart, wishlist, parts requests and integrated online payments
- Order tracking with delivery status, ratings, and returns

**Workshop management**
- Digital job cards: vehicle check-in reports, exterior inspection checks, and job card quotes
- Customer quotations: build, share and track quotes, including labour charges
- Customer payments: generate payment links and collect payments
- Service bookings and employee management

**Engagement**
- Wallet and reward redemption
- In-app learning videos with multi-language support
- Push notifications and deep links
- Embedded business dashboards/analytics for garage owners

## Tech Stack

| Area | Technologies |
|------|--------------|
| Language | Kotlin |
| UI | XML Views + ViewBinding/DataBinding, Jetpack Compose (Material 3), Navigation Component (Safe Args), Lottie |
| Architecture | MVVM, repository pattern, use cases, single-activity with fragments |
| Dependency Injection | Dagger 2 |
| Networking | Retrofit, OkHttp, Gson |
| Async | RxJava 2, Kotlin Coroutines |
| Local Storage | Room, Jetpack Paging 3, EncryptedSharedPreferences |
| Background Work | WorkManager |
| Camera & ML | CameraX, Google ML Kit Text Recognition |
| Maps & Location | Google Maps, Play Services Location |
| Payments | Razorpay |
| Firebase | Cloud Messaging, Crashlytics, Analytics, Performance Monitoring |
| Analytics | Mixpanel |
| Images | Glide, Coil |
| Build | Gradle, KSP, product flavors (staging / production), R8 minification |

## Architecture (high level)

```
UI (Fragments / Compose)
        │  observes LiveData / State
        ▼
   ViewModels ──► Use cases
        │
        ▼
   Repositories ──► Remote API (Retrofit)
                └──► Local cache (Room)
```

- Separate **staging** and **production** build flavors, with secrets kept out of source control
- Offline-friendly caching with Room and paginated lists with Paging 3
- Background sync and scheduled tasks with WorkManager
- Crash and performance monitoring in production with Firebase

## My Role

I handled the Android application end-to-end:

- **Requirements:** understood and broke down business requirements into app features
- **Development:** built UI and features using Kotlin and Java
- **Integration:** integrated REST APIs with the app
- **Testing & releases:** tested builds and managed staging and production releases on Google Play
- **Production support:** debugged and resolved production issues
- **Collaboration:** worked closely with the backend, QA and product teams to deliver and maintain the application

## Contact

<!-- Add LinkedIn / email if you want -->
