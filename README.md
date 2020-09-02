# OpenSilver.Documentation

## Where can I see the online OpenSilver documentation?

Click the following link to access the OpenSilver documentation:

http://doc.opensilver.net/

This repository contains the source code of the documentation. Feel free to send Pull Requests to fix the content of the documentation or add more content. For any questions, please feel free to contact us at: https://opensilver.net/contact.aspx

## How to compile the documentation?

After making changes to the source code of the documentation in this repository, you need to compile it in order to generate the HTML files of the documentation.

To do so, simply run the .BAT file named "**2. Generate HTML files from MD files.bat**", which is located in the root of this repository. This will generate HTML files in the "docs" subfolder of this repository.

To preview the result in the browser, simply run the .BAT file named "**3. Preview final result on Localhost.bat**". This will run a local server and open the documentation in a new browser window.

## How to deploy/publish the modified documentation?

After compiling and previewing the modified documenation according to the steps above, you just have to commit the modified files to the "master" branch of this repository to update the online documentation located at: http://doc.opensilver.net/ - The files in the "docs" subfolder of this repository are the HTML files that are displayed on the mentioned website.

## How to rebuild the "Reference" (API) section of the documentation to reflect the latest version of the OpenSilver source code?

The "reference" section is automatically generated by analyzing the source code of OpenSilver.

To update it, you first need to verify that the paths in the "docfx.json" file are correct. It should point to the location where the "CSPROJ" of the OpenSilver Runtime (https://github.com/OpenSilver/OpenSilver/tree/master/src/Runtime/Runtime) is located.
```
"metadata": [
  {
    "src": [
      {
        "files": [
          "../../OpenSilverDocumentation/OpenSilver/src/CSHTML5.Runtime/**.csproj"
        ]
      }
    ],
```

Then, run the .BAT file named "**1. Rebuild API documentation (only if source code has changed).bat**", which is located in the root of this repository. 

You will need to also run the other .BAT files to generate the HTML and see a preview of the result (to do so, refer to the sections above).

## How are the documentation source code files organized?

The .md files are the ones that contain the documentation pages. They use the Markdown syntax.

If you wish to preview Markdown files in Visual Studio, you can install the free extension named "Markdown Editor" by "Mads Kristensen" from:
https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor

The files used in the documentation are referenced in the ".JSON" file that is located in each folder.

All folders have the same structure:

* The ".MD" files are used to generate HTML pages. They are the ones to edit to change the content of a page.

* The "toc.yml" file references every file of the folder with a name and the path (href). yml files are space sensitive, meaning that each line must have a one tab indentation only.

Note: The "toc" file at the root of the project is slightly different because it is used to build the navbar and the sidebar. "Name" corresponds to the navbar tab name, "homepage" corresponds to the ".MD" file linked to the navbar, and "href" corresponds to the location where the sidebar (menu) is generated.

## How to customize the style and appearance of the documentation?

The "templates" folder has the following structure:

* The "fonts" folder contains all the fonts

* The "layout" folder contains the *"_master.tmpl"* file, which organizes the whole documentation structure. It is HTML-compatible, so you can add div elements to change the structure.

* The "partials" folder allow to organize small structure of the code, small div. Currently, the documentation uses the *".tmpl.partial"* files, the *".liquid"* seems unused. Here you can change the navbar layout ("navbar.tmpl.partial"), breadcrumbs ("breadcrumb.tmpl.partial"), toc ("toc.tmpl.partial"), etc.

* The "style" folder is resources folder that contains the *".css"* and the *".js"* files. The *"docfx.js"* & *"docfx.css"* are the default looks of the documentation. The *"docfx.vendor.js"* and the *"docfx.vendor.css"* are the responsive and functional part of the documentation. *"main.js"* & *"main.css"* contains all the custom styles.

## What if I have another question?

Please contact us for any questions at: https://opensilver.net/contact.aspx
