# Configurations

At this Admin panel, you can configure core features of your system.

Note: Please remember that values are not checked before saving! Make sure, that the values are valid for the configuration type (for example: do not enter "foo" in a **LONG** field).

**Note:** You need to be [bigace:manual:superuser](manual/superuser) OR own the “admin_configurations” permission

## Configuration packages

Find more information about special configurations in the following packages:

~~NOCACHE~~
`<nspages bigace:manual:configurations -simpleList -h1 -textPages="">`
## Configuration Types

The following types are known:

 | Config-type    | Description                           | Restriction        | 
 | -----------    | -----------                           | -----------        | 
 | **editor**     |                                       |                    | 
 | **string**     | Input field                           | max. 200 character | 
 | **adminstyle** |                                       |                    | 
 | **integer**    | Input field                           | only numbers       | 
 | **long**       | Input field                           | only numbers       | 
 | **boolean**    | TRUE(Yes)/FALSE(No)                   |                    | 
 | **timestamp**  |                                       |                    | 
 | **menu_id**    | select-box with menu tree popup       |                    | 
 | **timestamp**  |                                       |                    | 
 | **group**      | select-box of all existing usergroups |                    | 
 | **template**   |                                       |                    | 
 | **loglevel**   |                                       |                    | 
 | **language**   |                                       |                    | 
 | **category**   |                                       |                    | 
 | **design**     |                                       |                    | 

