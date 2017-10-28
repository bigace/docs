# Editor Framework

The Framework was made for simplifying the task "adding a new editor". This page shortly describes the available methods of the Editor Framework.
## PHP

Use the following methods when displaying your Editor:


*  **showEditorHeader();** - display the HTML for the page header

*  **showEditorFooter();** - display the HTML for the page bottom

# Requirements

An Editor has to implement ONLY the following Javascript functions, in order to fully integrate into the Editor environment.

The following methods must exist:


*  **getEditorContent()** - returns the current Editor content

*  **setEditorContent(html)** - sets the current Editor content

*  **isDirtyEditor()** - returns whether the content was edited since last save/load (if not supported always return true!)

*  **resetIsDirtyEditor()** - resets the state returned by isDirtyEditor(). Called for example after content was saved.


