# {last_created_items}

The {last_created_items} TAG returns an array of items that were lastly created.
It can return them from fetching them from a single submenu or from the complete community.

You have the option to get the array of items itself or you can let the TAG render html, so you don't have to struggle with the objects themself.

-> Since BIGACE 2.5.

## Attributes


*  **itemtype** - (optional, int, default: 1 for Menus)
    The itemtype to find last created items for.

*  **id** - (optional, int, default: not se)
    If set, items with this parent will be returned only. If not set, items from the whole community are fetched. 

*  **language** - (optional, string, default: current requested locale)

*  **from** - (optional, int, default: 0)

*  **to**/**amount** - (optional, int, default: 5) *both parameter are the same*

*  **order**

*  **assign** - (optional, string, not set)
    The name of the template variable the value will be assigned to. If value is not set the html is rendered, if set you will retrieve an array of items.

*  **pre** - (optional, string, default: `<li>`)

*  **post** - (optional, string, default: `</li>`)

*  **preDate** - (optional, string, default: `<i>`)

*  **postDate** - (optional, string, default: `</i>`)

*  **description** - (optional, int, default: -1)
    How to handle descriptions: -1 = hide description, 0 = full length, every other value = allowed length of description	

*  **date** - (optional, string, default: not set)
    If set the date of the creation is put out, if not set the date is skipped.

## Example

This example shows how to display a pre-rendered list of the last created items in the community.

	:::html
	`<html>`
	`<head>`
	   `<title>`The 10 last created items`</title>`
	`</head>`
	`<body>`
	   `<ul>`{last_created_items amount=10}`</ul>`
	`</body>`
	`</html>`

