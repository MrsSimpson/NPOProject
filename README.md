# NPOProject - Automate For A Cause - Helping Shelters 
*We developed this process in hopes of helping provide basic necessities and comforts to those in desperate need by enabling shelters to easily engage the community via social media with lists of their most needed items. This process should in turn help make shelter employees/volunteers lives easier, as well as, improve the lives of those who are facing some of their darkest times.*

-*Lacy Simpson, Virginia Hutchinson, Farrah Fouquet (The Bot Chix) 7/20/2019*

# Overview
This automated process will help shelters promote their needs to the public by checking an excel file that contains the shelter's in-stock items. If the quantity of items is below a minimum requriement (set by the shelter), the process will store this item in a list, and then it will post the list of items to the shelters facebook page.  
The organization updates and maintains the record of their in-stock items in the specified excel file. 
This process should help the shelter engage the community and make their needs known.
This software could be used for any type of shelter or organization. The test cases used for this process were for a fictitious homeless shelter and a fictitious animal shelter.
The process uses Facebook for the social media platform to post, but it could easily be enhanced to post needed items to Twitter, Instagram, and/or the organization's website.

## Automation Steps
This process will open and read all sheets in the provided excel file. 
The file will contain a list of in-stock-items for a shelter. (Column A)
For each item listed in the excel file, the process will check to see if the quantity of available items is below a specified amount Minimum (ColumnF).
If so, the name of the item (Column B) and a link to purchase the item (Column E) will be stored in a dictionary along with the quantity of items needed.
If items were stored in the dictionary, the process will invoke the postToFacebook workflow and pass the list of items as an argument.
If no items were stored, the process will end.<br>
The postToFacebook workflow will check to see if the user is logged in, if so the process will loop through the items in the list and post them in a message. If the user is not logged in, the process will get the username and password from the userCreds.xlsx file and log in. The process will then loop through the list of items in the dictionary that was passed in from the previous workflow. The list will contain the amount of the particular item that is needed, the name of the item needed, and a website link that list the item for purchase. An image will then be added to the post, and the post button is pressed. Google Chrome will be closed, and the process will end. 

## Software Needed To Run Process
* Microsoft Excel
* Google Chrome
* UiPath 2019.7.0-beta.74 - 7/15/2019 Community Edition
* Microsoft Windows 10
* .NET Framework Version 4.7.2 or later


# How to run the automation
* Clone the project from https://github.com/MrsSimpson/NPOProject
* Update the UserCreds.xlsx file with the username and password of the organization/person that will need to log in to post to Facebook. Update the username in the A2 cell and update the password in the B2 cell of the provided template.
* Update the imageFilePath variable that is in the postToFacebook Workflow. This file path must be the full path on your machine where the image will be located.
* If using a different excel file for the shelters stock besides the ones provided in the project repo, make sure the excel file being used has the correct format.<br> 
**The header of each sheet in the supply list excel file must be in the format:<br> In Stock (ColumnA) | Item (ColumnB) | Weight (ColumnC) | Avg. Price (ColumnD) | Link (ColumnE) | Minimum (ColumnF)** <br>
Please refer to the included **Homeless Mission Supply List.xlsx** OR **Humane Society Supply List.xlsx** for examples. 
<br>
* After adding the username and password to the userCreds.xlsx template, open the project in UiPath and update the file path to the image's location on the local machine. In the variable section of Main Workflow, ensure that the file names are set to the desired excel file that you would like the bot to read. Run the process from main. 

### Open Source License
Copyright 2019 Lacy Simpson, Virginia Hutchinson, Farrah Fouquet

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
