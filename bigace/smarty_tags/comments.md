# {comments}

The {comments} TAG is a multi-purpose TAG, both used for fetching and creating comments.

It is part of the [Comments Extension](extensions/addon/comments).


## Configuration

These configurations impact the behaviour of the TAG:


*  **use.captcha**

*  **email.required**

*  **allow.html**

Please read more about them [here](extensions/addon/comments#configuration).

## Attributes


*  **assign** - (__required__, int)
    The name of the template variable the comments will be assigned to. The returned/assigned value is an array of comments.

*  **preview** - (optional, boolean)
    Whether the preview of the last comment should be included or not.


__If you want to enable saving of comments:__

*  **post** (required, boolean) - since 1.1
    Whether posted comments should be saved or ignored.

*  **admin** (required, string)
    Name of the smarty variable where the feedback is added to (see below).


__Pass information for which item you want to fetch and save comments for:__

*  **item** (required, Item)
    The Item to fetch the comments for.

OR


*  **id** (required, int)
    The Item ID to fetch comments for.

*  **language** (required, string)
    The language to fetch comments for.

*  **itemtype** (optional, int) 
    The Itemtype to fetch comments for. Default is "1" for menus.

## "admin" feedback variable

The following keys are in the "admin" feedback variable:


*  **missing**
    If someone tried to post a comment, this array holds the keys of the missing values (array is empty if none was missing). Possible keys are: "name", "email", "comment" and "captcha".

*  **mode**
    The mode that was executed. Possible modes are: "preview" and "create".

*  **spam**
    If this comment was spam, this key is set with true as value.


## Example

For a full example, please have a look into the **Comments-Listing-Form.tpl** include, which is shipped with the Comments Extension.

