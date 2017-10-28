# {faq_latest}

The {faq_latest} TAG fetches the latest FAQ entries from all categories.

## Attributes


*  **assign** - (__required__, string)
    The name of the template variable the result array will be assigned to.

*  **order** - (optional, string)
    Default order is **DESC**, Possible values are **ASC** and **DESC**.

*  **start** - (optional, int)
    The first value to fetch. Default is 0.

*  **end** - (optional, int)
    The last value to fetch. Default is 10.

## Example

This fetches the last 10 FAQ entries.

	:::html
	`<html>`
	`<head>`
	   `<title>`Latest 10 FAQs`</title>`
	`</head>`
	`<body>`
	   {faq_latest assign="entries"}
	   {foreach from=$entries item="faq"}
	     `<div class="faqEntry">`
	       `<b>`Question`</b>`: {$faq.question}
	       `<br />`
	       `<b>`Answer`</b>`: {$faq.answer}
	     `</div>`
	   {/foreach}   
	`</body>`
	`</html>`

