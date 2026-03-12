# Stash — Personal Budget Tracker

**Group 5 | PROG7313 | POE Part 1**

---

> ⚠️ **Note:** This commit contains **UI scaffolding only**.
> No backend, database, authentication logic, ViewModels, or LiveData have been implemented yet.
> All screens are purely layout/navigation scaffolding with placeholder data.

---

## App Overview

**Stash** is a personal budget tracker Android application that helps users take control of their finances through expense tracking, budget goal setting, spending visualization, and gamified achievements.

---

## Tech Stack

| Item | Detail |
|------|--------|
| Language | Kotlin |
| Min SDK | API 24 (Android 7.0) |
| Target SDK | API 34 |
| UI | XML Layouts with View Binding |
| Navigation | Android Navigation Component |
| Charts | MPAndroidChart v3.1.0 |
| Theme | Material3 (DayNight.NoActionBar) |

---

## Colour Palette

| Name | Hex | Usage |
|------|-----|-------|
| colorPrimary | `#1B2A4A` | Dark navy — toolbar, buttons |
| colorAccent | `#C9982A` | Gold — FABs, highlights |
| colorBackground | `#B8D8D8` | Light teal/sage — launcher background |
| colorAppBackground | `#F4F9F9` | Very light teal-white — screen backgrounds |
| colorSurface | `#FFFFFF` | Cards and surfaces |
| colorError | `#B00020` | Error states |
| colorSuccess | `#2E7D32` | Success states |
| colorWarning | `#F57C00` | Warning / streak icons |

---

## Navigation Structure

```
AuthActivity (launcher)
├── LoginFragment          (auth_nav_graph — start destination)
└── RegisterFragment

MainActivity
├── DashboardFragment      (bottom nav — home)
├── ExpensesFragment       (bottom nav — receipt)
├── BudgetGoalsFragment    (bottom nav — wallet)
├── SpendingGraphFragment  (bottom nav — bar chart)
├── AchievementsFragment   (bottom nav — star)
│
├── AddExpenseFragment     (FAB from Dashboard / Expenses — no bottom nav)
├── CategoriesFragment     (from Budget Goals — no bottom nav)
└── SettingsFragment       (from Dashboard toolbar — no bottom nav)
```

---

## Screens Built

1. **Login** — Logo, tagline, username/password fields, login button, register link
2. **Register** — Back arrow, all registration fields, register button, login link
3. **Dashboard** — Greeting, motivational banner, overall budget progress, category progress cards, XP/streak row, FAB
4. **Expenses** — Date range filter, search bar, expense card list with 5 placeholder items, FAB
5. **Add/Edit Expense** — Amount (large), date, start/end time, description, category dropdown, photo attach, recurring toggle + frequency dropdown
6. **Categories** — Category list with colour dots and edit icons, FAB, add/edit bottom sheet with colour picker
7. **Budget Goals** — Overall monthly min/max fields, category goal rows with min/max inputs, Manage Categories button
8. **Spending Graph** — Date range, MPAndroidChart bar chart with dummy 7-day data, dashed min/max goal lines, category legend
9. **Achievements** — Level/XP card, 6 badge cards in 2-column grid (3 earned + 3 locked)
10. **Settings/Profile** — Avatar with initials, username/email, Change Password, Dark Mode toggle, Biometric toggle, Notifications toggle, Log Out button

---

## Project Structure

```
app/src/main/
├── java/.../
│   ├── MainActivity.kt
│   ├── AuthActivity.kt
│   ├── model/
│   │   ├── Badge.kt
│   │   ├── Category.kt
│   │   ├── CategoryProgress.kt
│   │   └── Expense.kt
│   ├── adapters/
│   │   ├── BadgeAdapter.kt
│   │   ├── CategoryAdapter.kt
│   │   ├── CategoryGoalAdapter.kt
│   │   ├── CategoryProgressAdapter.kt
│   │   └── ExpenseAdapter.kt
│   └── ui/
│       ├── auth/LoginFragment.kt, RegisterFragment.kt
│       ├── dashboard/DashboardFragment.kt
│       ├── expenses/ExpensesFragment.kt, AddExpenseFragment.kt
│       ├── budget/BudgetGoalsFragment.kt, CategoriesFragment.kt
│       ├── graph/SpendingGraphFragment.kt
│       ├── achievements/AchievementsFragment.kt
│       └── settings/SettingsFragment.kt
└── res/
    ├── drawable/          (vector icons, backgrounds)
    ├── layout/            (all screen and item layouts)
    ├── menu/              (bottom_nav_menu.xml)
    ├── navigation/        (nav_graph.xml, auth_nav_graph.xml)
    └── values/            (colors.xml, strings.xml, dimens.xml, themes.xml)
```

---

## What's Next (Part 2)

- Room database for expenses, categories, and goals
- ViewModel + LiveData for reactive UI
- Working authentication (local or Firebase)
- Functional date pickers and camera integration
- Real MPAndroidChart data from database
- Dark mode implementation
- Biometric login
