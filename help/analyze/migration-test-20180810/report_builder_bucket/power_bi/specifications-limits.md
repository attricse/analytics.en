---
description: null
seo-description: null
seo-title: Limitations and specifications
title: Limitations and specifications
uuid: 6f30cd48-cb87-48b3-81d8-8eb4de7de94a
index: y
internal: n
snippet: y
translate: y
---

# Limitations and specifications


* [ Power BI Publishing Restrictions ](specifications-limits.md#section_D4BDD70B20F94A0FAE53531CA528AE42)
* [ Editing a Report Builder Request after Publishing to Power BI... ](specifications-limits.md#section_6989E74F68DD43F08D37C36B6777DB50)
* [ Changing the Name of a Power BI Report ](specifications-limits.md#section_2E7893A78B914EBFACB2B08CBD9E472E)

## Power BI publishing restrictions {#section_D4BDD70B20F94A0FAE53531CA528AE42}


>[!NOTE]
>
>These restrictions apply only to the option "Publish Report Builder Requests as Power BI Dataset Tables".



* A maximum of 100 Report Builder requests can be exported to Power BI per workbook.
* The scheduling process will stop exporting requests when the 101th request is reached.
* Only the first 10,000 rows of Analytics data will be sent to Power BI per Report Builder request. The remaining rows will be ignored.

## Edit a Report Builder request after publishing to Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}


>[!NOTE]
>
>This specification applies to the options "Publish All Report Builder Requests as Power BI Dataset Tables" and "Publish All Formatted Tables in the Workbook as Power BI Dataset Tables".



Editing a Report Builder request after publishing it to Power BI may cause problems. 


* **Case 1**: You publish a workbook to Power BI and create a visualization based on its data. Next, you make changes to the workbook, causing one of the columns of the data set that it references to disappear. Then you republish. This will break the visualization in Power BI. **Here is an example of how the visualization WILL break:** 

    1. In Report Builder, create a workbook with one request, using the Page dimension and the Page Views metric.
    1. [ Schedule this request ](whats_new_arb.md#section_0C26057C7DBB4068A643FDD688F6E463) to be published to Power BI.
    1. In Power BI, create a visualization for Page and Page Views.
    1. Now edit the workbook by removing Page Views from the request.
    1. Edit the schedule with the updated workbook and re-publish the request to Power BI.
    1. Once the new workbook is sent to Power BI     
        1. Verify that it overwrote the existing dataset that was created when you first published.
        1. Verify that the page_1 table is properly updated with the Page and Visits columns.
        1. Verify that your visualization is broken, since it references the Page Views column that is no longer present in the page_1 table.

  **Here is an example of how the visualization will NOT break:** 

    1. In Report Builder, create a workbook with one request, using the Page dimension and the Page Views metric.
    1. [ Schedule this request ](whats_new_arb.md#section_0C26057C7DBB4068A643FDD688F6E463) to be published to Power BI.
    1. In Power BI, create a visualization for Page and Page Views.
    1. Now edit the workbook in Report Builder, adding the Visit metric while keeping Page and Page Views.
    1. Edit the schedule with the updated workbook and re-publish the request to Power BI.
    1. Once the new workbook is sent to Power BI     
        1. Verify that it overwrote the existing dataset that was created when you first published.
        1. Verify that the page_1 table is properly updated with the Page, Page Views, and Visits columns.
        1. Verify that your visualization continues to work properly, since it references two columns that are still present in the page_1 table.


* **Case 2**: You pin a section of your workbook to a dashboard in Power BI and you later remove that pinned section (such as a chart or a table) from the workbook. This will break the visualization.


## Change the name of a Power BI report {#section_2E7893A78B914EBFACB2B08CBD9E472E}

By default, the name will be populated from the workbook filename (without the .xlsx extension), except that spaces are replaced with underscore characters. 

Keep in mind that 

* The label cannot be a combination of letters and numbers that could be mistaken for a row and column address. For example, A100 cannot be a label because it is the address of a cell in a worksheet.
* The following characters are not valid label characters: '#', '@', '!', '$', '^', '&amp;amp;', '*', '`', '~', ' ' . They will be replaced by an underscore character.
* When you enter an invalid name, a warning message will be shown that will suggest an auto-generated name. If you click ** [!UICONTROL  Yes] **, this name will be used. If you click ** [!UICONTROL  No] **, the Advanced Wizard UI will let you enter the new name.