# {explode}

The {explode} Modifier splits after a defined delimiter.
Use this mod with e.g. the {assign}-TAG.

## Attributes

*  **var** - (__required__,string)

*  **value** - (__required__,string)

## Syntax

	:::html
	{assign var="DEFINED_VAR" value="DEFINED_VALUE"|VAR_TO_EXPLODE}


## Example

	:::html
	{assign var="stuff" value=";"|explode:$MENU->getCatchwords()}
	`<ul>`
	`<li>`Item 1:`</span>` {$stuff[0]}`</li>`
	`<li>`Item 2:`</span>` {$stuff[1]}`</li>`
	`<li>`Item 3: {$stuff[2]}`</li>`
	`</ul>`

