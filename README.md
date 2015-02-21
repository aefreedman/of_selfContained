# of_selfContained
This is a self-contained OpenFrameworks project with the OF library included inside the project's path. It will use more space that making projects inside a common OF release folder, but is more convenient when you need to package OF projects in a way that makes them easier to archive or share with collaborators via source control.

This project uses the of_v0.8.4_osx_release but is easily changed by replacing the OF project folder with the version of your choice.

This project can be copied and reused as a template for any new OF project.

The steps taken to create this project are detailed below:

1. Take a new OF project made by the project generator or the example project in the OF release and put it wherever you like
2. Inside your project's folder, create a new folder and call it "libs" or "libraries" or whatever you like
3. Take the OF OSX release folder and put it inside this library folder; *make sure you keep the folder structure intact* (you can delete all the folders in the release except "lib")
4. open your project in Xcode
5. The OF project inside your project will be missing (red); delete it and add your project-local OF .xccodeproj by navigating to ../libs/openFrameworksCompiled/project/osx and dragging the project into your project's workspace
6. Edit your project's Project.xcconfig to reflect your custom OF_PATH and the include path to the OF project's CoreOF.xcconfig file (e.g. OF_PATH = libraries/of_v0.8.4_osx_release instead of ../../../..)
7. In Targets > Buid Phases > Target Dependencies : add openFrameworks
7. In Targets > Build Phases > Link Binary With Libraries : add openFrameworksDebug.a
8. in Targets > Build Phases > Run Script > edit the first line to match the OF_PATH you defined in Project.xcconfig
9. Done
