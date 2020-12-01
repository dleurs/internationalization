# Internalisation

Implementing Internalisation only of the fluter-starter project

Localisation requires the Flutter Intl plugin (available on VSCode and IntelliJ marketplaces)
Needs to be installed to properly add and manage new supported locales

- Flutter Intl on Android Studio (IntelliJ)
- Flutter Intl on VSCode

![Demo App](/assets/demo-app.gif)

Check this URL for information :<br/>
https://marketplace.visualstudio.com/items?itemName=localizely.flutter-intl

- Add to podspec.yaml
```yaml
#dependencies:
#  flutter:
#    sdk: flutter
  flutter_localizations:
    sdk: flutter
  intl: ^0.16.1
  intl_utils: ^1.8.0
```

```bash
flutter pub get
```

- Initialise, cmd-vscode : Flutter Intl: Initialize
- ios/Runner/Info.plist add 
```bash
<key>CFBundleLocalizations</key>
<array>
    <string>en</string>
    <string>fr_FR</string>
    ...
</array>
```

- Add to your MaterialApp()
```dart
localizationsDelegates: [
S.delegate,
GlobalMaterialLocalizations.delegate,
GlobalWidgetsLocalizations.delegate,
GlobalCupertinoLocalizations.delegate,
],
supportedLocales: S.delegate.supportedLocales,
```
- Add language, cmd-vscode : Flutter Intl: Add locale
- Create / modify .arb files, put them inside lib/l10n (always replace existing)
- Inside Text widget, add something like S.of(context).my_name
- Finito


To check plural :<br/>
https://pub.dev/documentation/intl/latest/intl/Intl/plural.html

To check gender : <br/>
https://pub.dev/documentation/intl/latest/intl/Intl/gender.html

Other demo :<br/>
https://github.com/localizely/flutter-intl-plugin-sample-app

Youtube video :<br/>
https://www.youtube.com/watch?v=MQo32dQxxjg

Localizely :<br/>
https://localizely.com/flutter-localization-workflow/<br/>
Connecting with Localizely ID project and Key did not work. Import / export arb

Localise has got a good interface for translation <br/>
You can import / export .arb files<br/>
![ScreenshotLocalizely](/assets/ScreenshotLocalizely.png)


Bonus, change language in settings<br/>
![Demo App](/assets/internalisation-settings.gif)