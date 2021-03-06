# VS 2017 RESX bug
This repository illustrates a Visual Studio 2017 localization issue.

## Brief description

The sample app contains a UWP app and a PCL library with localized RESX file (*LocalizedStrings.rex, LocalizedStrings.cs.resx*). Culture is set in the app's constructor as follows:

    CultureInfo.CurrentUICulture = new CultureInfo("cs");
    CultureInfo.CurrentCulture = new CultureInfo("cs");

When launched for debugging, the localized resources are never displayed and the app will show neutral RESX strings only. When debugged in Visual Studio 2015, it works as expected.

## Steps to reproduce
1. Clone the repo
2. Open the solution VSResxIssue\VSResxIssue.sln in Visual Studio 2017
3. Clean the solution
4. Debug UWP app on Local Machine in x86
5. The text in the launched app will read *Neutral* (neutral resource is loaded)
6. Close VS 2017
7. Open the solution in Visual Studio 2015
8. Clean the solution
9. Debug UWP app on Local Machine in x86
10. The text in the launched app will read *Localized* (localized cs resource is loaded)

## Expected behavior

Text should read *Localized* in step 5.

## Additional info

I have observed that this problem occurs only for Debug build. Release build loads the localized resources even in VS 2017.

## Version info

- Microsoft Visual Studio Enterprise 2017 Version 15.0.26228.9
- Microsoft .NET Framework Version 4.6.01586
- Visual Studio Tools for Universal Windows Apps   15.0.26228.00
- Xamarin   4.3.0.784

## Screenshots

### Setp 5 (VS 2017)

![VS 2017](https://raw.githubusercontent.com/MartinZikmund/vs2017-resx-issue/master/vs2017.PNG)

### Step 10 (VS 2015)

![VS 2017](https://raw.githubusercontent.com/MartinZikmund/vs2017-resx-issue/master/Vs2015.PNG)
