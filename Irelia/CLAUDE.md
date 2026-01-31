# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Irelia is an iOS login application built with a hybrid Objective-C and Swift architecture. It implements a login interface with form validation, custom UI components, and social login placeholders (Apple and WeChat).

## Build and Run

Open `Irelia.xcodeproj` in Xcode and build/run using standard Xcode commands:
- **Build**: Cmd+B or `xcodebuild -project Irelia.xcodeproj -scheme Irelia build`
- **Run**: Cmd+R in Xcode

Target: iOS (iPhone portrait, iPad all orientations)

## Architecture

### Swift-Objective-C Bridge
- Entry point: `main.m` → `AppDelegate.m` (Objective-C)
- Bridge header: `Irelia-Bridging-Header.h` enables Swift code to use Objective-C classes
- All UI code is in Swift

### Code Organization
```
Irelia/
├── Controllers/    # View controllers (LoginViewController.swift - main screen)
├── Views/          # Reusable UI components (CustomTextField, ErrorView)
├── Utils/          # Helpers (FormValidator, UIColor+Hex extension)
└── Resources/      # Storyboards and assets
```

### Key Components
- **LoginViewController**: Main login screen with username/password fields, validation, and social login buttons
- **CustomTextField**: UITextField subclass with left/right icon support and tap callbacks
- **ErrorView**: Error message display with icon
- **FormValidator**: Static validation methods for username, password, email, and Chinese phone numbers

## Design System Colors

| Purpose | Hex |
|---------|-----|
| Primary (Purple) | #8B5CF6 |
| Text Primary | #18181B |
| Text Secondary | #71717A |
| Text Tertiary | #A1A1AA |
| Error | #EF4444 |
| Input Background | #F4F4F5 |
| WeChat Green | #07C160 |

## Validation Rules (FormValidator.swift)

- Username: 3-20 characters, alphanumeric + underscore
- Password: 6-20 characters
- Phone: Chinese mainland format (1[3-9]xxxxxxxxx)
- Email: Standard RFC format
