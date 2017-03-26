# VS 2017 RESX bug
This repository illustrates a Visual Studio 2017 localization issue.

## Brief description

When a UWP app references a Portable Class Library with localized RESX file and the app is then launched for debugging, the localized resources are never displayed and the app will show neutral RESX strings only. When debugged in Visual Studio 2015, it works as expected.

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
