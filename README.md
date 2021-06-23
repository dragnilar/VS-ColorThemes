# This fork contains a version intended for Visual Studio 2022
- This fork specifically was made to provide a version that supports VS 2022. It does not support any of the prior versions and it does not add any new functionality. 
- You can either build this using VS 2019, VS 2022 or download the VSIX package from the [Releases Page](https://github.com/dragnilar/VS-ColorThemes/releases).
- I most likely will not try to merge this back into the original branch since Microsoft seems to have officially abandoned it. 
- 

## Using this Extension

1. Download and install the extension
1. Restart Visual Studio
1. Navigate to _Tools > Options > Environment > General_ and select your color theme:
   ![](https://user-images.githubusercontent.com/350947/69694799-25e2a680-112e-11ea-85d0-f6fe476168d5.png)


## Steps to create a custom theme for Visual Studio 2022 (in case you don't like the ones that come with this extension)
0. Prerequisite:
* Using **Visual Studio 2019** install the optional Theme editor VSIX package from here: [Visual Studio Theme Color Theme Designer](https://marketplace.visualstudio.com/items?itemName=ms-madsk.ColorThemeDesigner).
1. Go to Tools -> Customize Colors (CTE extension), or File -> New -> Project and create a VSTheme Project (CTD extension).
2. Hover over the original theme you want to edit and click on 'Create Copy of Theme'.
3. Hover over the Custom Theme you created, and click on 'Edit Theme'.
4. Edit the colors to create a new custom theme.
5. Build the project, it should output a VSIX file in your bin folder.
6. Copy the VSIX file so you have a backup of it.
7. Rename the VSIX file to .zip and unzip it. You can also open it up using an archive manager such as 7Zip.
8. Edit the following 3 files: extension.vsixmanifest, catalog.json, manifest.json
9. In extension.vsixmanifest, you need to change the upper bound supported version from 17 to 18 in the InstallationTarget and Prerequisite elements. Also for the installation target, you need to add the subnode for ProductArchitcture and give it the value amd64.
![UpdateManifest](https://user-images.githubusercontent.com/33742520/123148226-f856ff80-d42d-11eb-9b0e-3dac7d1bd638.png)
11. In catalog.json and manifest.json, change the two spots that specify the upper supported version from 17 to 18.
![UpdateCatalogAndManifestJson](https://user-images.githubusercontent.com/33742520/123148236-fab95980-d42d-11eb-911e-f7ed7e77b273.png)
12. Zip the folder you edited in the files within just now into a .zip folder. Rename the .zip file to .vsix.
13. Open the VSIX file and run it. If everything was done correctly, the VSIX installer should see Visual Studio 2022 Preview and install your theme for you.
