# This fork contains a version intended for Visual Studio 2022
- This fork specifically was made to provide a version that supports VS 2022. It does not support any of the prior versions and it does not add any new functionality. 
- In addition to the VS-ColorThemes extension, this fork also contains a version of the Visual Studio Theme Editor that targets VS 2022 (in case you want to make your own themes).
   - Since the Theme Editor is not open sourced, I had to manually edit the VSIX file to get it to work with VS 2022. Whatever issues it had in VS2019, it most likely will still have in VS 2022.
- You can either build this using VS 2019, VS 2022 or download the VSIX package from the [Releases Page](https://github.com/dragnilar/VS-ColorThemes/releases).
- I most likely will not try to merge this back into the original branch since Microsoft seems to have officially abandoned it.

## Using this Extension

1. Download and install the extension
1. Restart Visual Studio
1. Navigate to _Tools > Options > Environment > General_ and select your color theme:
   ![](https://user-images.githubusercontent.com/350947/69694799-25e2a680-112e-11ea-85d0-f6fe476168d5.png)


## Steps to create a custom theme for this project
0. Prerequisite:
* For **Visual Studio 2022**, install the optional Theme editor VSIX package that comes with this extension (it can be found in the AdditionalVSIX folder).
1. Go to Tools -> Customize Colors (CTE extension), or File -> New -> Project and create a VSTheme Project (CTD extension).
2. Hover over the original theme you want to edit and click on 'Create Copy of Theme'.
3. Hover over the Custom Theme you created, and click on 'Edit Theme'.
4. Edit the colors to create a new custom theme.
5. Click on the Export Theme icon at the top and save the new theme as a vstheme. Then rename the file to xml.
6. Create a fork of the repo for your theme and add the file within the Themes folder.
7. Also update:

    a. The ThemeRegistration.pkgdef file (Please add entries in alphabetical order and rootkey token from the GUID of the xml file)
    
    b. The VSColorThemes.csproj file (include the theme file to the project)
    
    c. The source.extension.manifest (don’t update the version – just add to the assets)

**NOTE: Please check the [ShellColorTokens.md](https://github.com/microsoft/VS-ColorThemes/blob/master/ShellColorTokens.md) to ensure your theme contains all of the color tokens listed therein.**
