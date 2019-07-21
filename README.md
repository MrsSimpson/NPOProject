# NPOProject - Automate For A Cause - Helping Shelters 
*We developed this process in hopes of helping provide basic necessities and comforts to those in desperate need by enabling shelters to 
easily engage the community via social media with lists of their most needed items. This process should in turn help make shelter 
employees/volunteers lives easier, as well as, improve the lives of those who are facing some of their darkest times.*

-*Lacy Simpson, Virginia Hutchinson, Farrah Fouquet (The Bot Chix) 7/20/2019*

# Overview
This automated process will check to see if the shelter is in need of particular items. 
The organization updates and maintains a record of their items in-stock in the specified excel file. 
If the shelter is low on certain items, the process will navigate to the organization's Facebook page to post a message listing the needed items which, in turn, should help the shelter engage the community and make the shelter’s needs known.
This software could be used for any type of shelter or organization. The test cases used for this process were for a fictitious homeless shelter and a fictitious animal shelter.
The process uses Facebook for the social media platform to post, but it could easily be enhanced to post needed items to twitter, Instagram, and/or the organization's website.
## Process Steps
This process will open and read the provided excel file. 
The file will contain a list of in-stock-items for a shelter. (Column A)
For each item listed in the excel file, the process will check to see if the quantity of available items is below a specified amount.
If so, the name of the item (Column B) and a link to purchase the item (Column E) will be stored in a dictionary.
If items were stored in the dictionary, the process will navigate to Facebook and post a message listing the items with corresponding links. 
If no items were stored, the process will end.

## Software Needed To Run Process
* Microsoft Excel
* Google Chrome
* UiPath Community Edition

# Notes
* Update the UserCreds.xlsx file with the username and password of the organization/person that will need to log in to post to Facebook.
* Update the imageFilePath Variable that is in the postToFacebook Workflow 
* Make sure the Supply list .xlsx file being used has the correct template. <br> 
**The header of each sheet in the supply list excel file must be in the format:<br> In Stock (ColumnA) | Item (ColumnB) | Weight (ColumnC) | Avg. Price (ColumnD) | Link (ColumnE)** <br>
Please refer to the included **Homeless Mission Supply List.xlsx** OR **Humane Society Supply List.xlsx** for examples

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
