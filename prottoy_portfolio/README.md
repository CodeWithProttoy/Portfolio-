# Prottoy Dhar — Portfolio App (Flutter + GetX)

## Setup
1. Unzip and open the folder in your editor.
2. Run:
   ```
   flutter pub get
   flutter run
   ```
3. Your uploaded photo is already placed at `assets/images/profile.jpg` and registered in `pubspec.yaml`.

## Architecture (GetX)
- `lib/core/controllers/` — `ThemeController` (light/dark + gradient state) and `PortfolioController` (all portfolio data + animation triggers).
- `lib/core/bindings/app_binding.dart` — injects controllers via `Get.put`.
- `lib/core/routes/` — `GetPage` route table (`AppRoutes`, `AppPages`) with fade transition, ready to extend with more screens.
- `lib/screens/home/` — UI, built with `Obx()` reactive widgets that read from the controllers (no `setState` for app data — only used locally for press/tap animation states).

## Animations implemented (size + color transition)
1. **Theme toggle button** (`theme_toggle_button.dart`) — pill resizes and swaps color between warm/cool palettes.
2. **Profile avatar** (`profile_header.dart`) — tap to grow the ring and shift its glow color.
3. **Skill bars** (`skills_section.dart`) — width animates 0 → skill level and fill uses the active theme gradient.
4. **Project cards** (`projects_section.dart`) — press-scale + border/background color transition toward the accent gradient.

## Update your content
Edit `lib/core/controllers/portfolio_controller.dart` to change bio, skills, projects, email, phone, or Facebook link — everything else updates automatically since the UI is fully reactive.

## Notes
- Replace `assets/images/profile.jpg` any time with a new photo of the same filename, or update the path in `portfolio_controller.dart`.
- Add more projects/skills by simply adding entries to the lists — UI scales automatically.
