## 0.0.2+dlct.1 (DayLight Creative Technologies fork)

### material_ui migration

- Migrated from `package:flutter/material.dart` to the standalone
  `package:material_ui` / `package:cupertino_ui` packages via the official
  `dart fix --apply --code=migrate_design_widgets` (2 fixes in 2 files).

**Why this fork exists.** Flutter 3.47 decoupled Material and Cupertino from the
framework into standalone packages under `flutter/packages`. `material_ui`
re-exports only `package:flutter/widgets.dart` and **redefines** the material
layer, so `material_ui.ThemeData` / `TextTheme` / `InputDecoration` /
`ThemeExtension` / `TabController` are DIFFERENT CLASSES from their
`package:flutter/material.dart` counterparts. An app that has migrated cannot
exchange material-layer types with a package that has not — it is a compile
error, and `MaterialUiCompatibilityBridge` does not help because that is a
runtime widget for inherited `ThemeData`/`MaterialLocalizations`, not a type
bridge.

SocialScoreKeeper migrated on 2026-09-20. Upstream contentsize_tabbarview 0.0.2 had not, and
was one of three packages blocking the migration.

**Return to pub.dev when** upstream contentsize_tabbarview ships a release that depends on
`material_ui`. At that point drop the git pin and this fork entirely — there is
no DLCT-original behaviour here, only the import migration.

Based on upstream `contentsize_tabbarview` **0.0.2** (published pub.dev source).


# 0.0.2 
## Dated - 2023-10-07
### Added

- Initial release of the Flutter package.
- Added a `ContentSizeTabBarView` widget.
- Allows resizing of tab bar view to fit its content size.

