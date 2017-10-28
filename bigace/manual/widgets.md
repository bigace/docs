# Widgets

Widgets are small HTML snippets, that will be displayed on your page.
It depends on your Layout if you can use widgets or not, the designer can choose to support widgets or not.

__Note:__ *Widgets were called **Portlets** in Bigace v2, but the naming was changed. Many softwares nowadays use the word "Widgets" instead of "Portlets" and we therefor decided to change the wording, so Bigace is more easy to understand for new users.*

You can configure used widgets through the "Widget admin", as seen in this screenshot:

{{:bigace3:manual:widgets:screenshot_004.png|Widget administration}}
 1.  Available widgets: A list of all available widgets for your system
 2.  Details: The details of the currently choosen widget from list 1)
 3.  Button down: To use a widget in the current page, you have to configure it in 2) and then move it down into the list of active widgets 4)
 4.  Active widgets: The list of all active widgets for the current page in the order they will be displayed
 5.  Reorder widgets: To display the active widgets in a different order, select one in list 4) and use the up-and-down buttons to move/reorder it within the list.
 6.  Remove widget: To remove a widget from the list of active widgets 4) select it and then click the trashbin.
 7.  Save: To use the applied changes, click the save button, close the "Widget admin" and reload the original page.

Please note: If your template supports multiple widget columns, you might see element 3 - 6 multiple times

## Which widgets will be displayed

If a page has no widgets, the system will look up through all parent pages to the top-level page if there are widgets configured. The first result will then be used as widgets for the current page.

For example if you have this navigation with explicit configured widgets in (brackets):


*  Top-Level (Widgets: e,c,a)
    * Page 1
      * Page 1.1 (Widgets: a,b)
        * Page 1.1.1 
      * Page 1.2
    * Page 2 (Widgets: d)
      * Page 2.1 
        * Page 2.1.1
        * Page 2.1.1
      * Page 2.2 (Widgets: d,a)
        * Page 2.2.1 (Widgets: a,b,c)

Then you will see the following:


*  Top-Level (e,c,a)
    * Page 1 (e,c,a)
      * Page 1.1 (a,b)
        * Page 1.1.1 (a,b) 
      * Page 1.2 (e,c,a)
    * Page 2 (d)
      * Page 2.1 (d) 
        * Page 2.1.1 (d)
        * Page 2.1.1 (d)
      * Page 2.2 (d,a)
        * Page 2.2.1 (a,b,c)


## See also

*  [widgets() ViewHelper](bigace/developer/viewhelper/widgets)

*  [bigace:developer:zendtemplate](bigace/developer/zendtemplate)

