# cid{CID}

If many documentation parts, you can read about a path **/consumer/cid{CID}/...** or **/public/cid{CID}/...**.

What is it all about this cid{CID} thing now?

To start from scratch, BIGACE has 5 base directorys:


*  addon

*  consumer

*  misc

*  public

*  system

In this topic, we discuss both the the **consumer/cid{CID}/** and **public/cid{CID}/** directories. In **consumer/** is all Community depend data stored and **public/** holds the files, accessible from your web-browser (like design images or stylesheet).
Each Community has its one subdirectory that is named "cid{CID}" where {CID} stands for the internal Community ID.

Assume, you are running only one Community, which has the ID 1, your data path is **consumer/cid1/**, your web path is **public/cid1/**.

If you read something like "Change your file /consumer/cid{CID}/foo/bar.php" the path "/consumer/cid1/foo/bar.php" is meant (unless nothing else is said).

## Consumer vs. Community

In earlier versions, the naming for one community was consumer (for what reason ever LOL).

Both words stand for the same, for one website (not page!) in your system. Don't be irritated ^^


## Community ID

To find out, which Community ID your website has, you can open the source code of any page in your browser and scroll down to the bottom.
There is a hidden footer, that holds the information you need ("Community").

The otherway to find your Community ID is to open the Administration and choose "Community/Administration" (you need Administrator privileges to see it). There are all installed Communitys visible and you only have to watch out for the "Community ID" flag.

## And what is consumer/cid{CID}/

There is a special path, which is really named **consumer/cid{CID}/**. This is a "template" path for all new Communitys.

If you create a new Community, all data is fetched from this directory and copied to the new community directory.
You should not change files in there, unless you really know what you do or you are asked to do it!


