# Transferring Data with Globus

All large files should be transferred to KBase using Globus. The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 GB.

Globus is a data management and file transfer system that can facilitate bulk transfer of data \(either large data files or a large number of files\) between two endpoints. The endpoints that apply here are KBase, JGI, and your local computer. The KBase endpoint is called “KBase Bulk Share,” and JGI has their own way to link to Globus. To do any transfer using Globus, you will [need a Globus account](https://www.globusid.org/create).

Your local computer can become a Globus endpoint with a Globus Connect Personal Endpoint \(see instructions [here](https://docs.globus.org/how-to/)\). This is necessary for transfers to or from your local computer.

Once you have a Globus account, it needs to be linked to your KBase account. For help with this, see “Create or modify your user Profile” [here](../getting-started/narrative-user-guide/share-narratives.md).

To initiate a transfer using Globus, click “Or upload to this staging area by using Globus Online” in the Import tab.

![](http://kbase.us/wp-content/uploads/2018/01/Screen-Shot-2018-01-24-at-1.54.06-PM.png)

That should bring you to a page that looks something like this \(assuming you have a Globus account\):

![](http://kbase.us/wp-content/uploads/2019/07/Globus-Screenshot.png)

The panel on the right should be set to “KBase Bulk Share,” which is your staging area. In the example above, the share point is at the root directory, and the user _landml_ needs to click on their individual directory. If needed, Globus can be used to create new directories in your staging area for your transfer and can be used to delete staging files when you are done importing into KBase.

Set the left panel to the location of the data you want to transfer \(i.e. you could choose the JGI endpoint they send via email\). On the KBase endpoint, if you don’t see a directory with your name as in the example above, add /username to the Path for the KBase endpoint \(/landml is used in the example above\).

You should then be able to drag data files or folders from the left endpoint to the right one, inside the Globus interface, and the files will appear in your KBase staging area.

Your transfer request will be submitted to Globus. If there are network or other problems, Globus will retry several times before giving up. Globus will send an email when the transfer is complete. In the KBase staging area, you may need to click on the refresh button \(to the left of the user name\) to update the Import panel.

![](http://kbase.us/wp-content/uploads/2019/07/landml-refresh.png)

[This page](../getting-started/narrative-user-guide/add-data-to-your-narrative.md) has more information about how to add data to your KBase account so you can analyze it.

**Firewalls**

Some government institutions have a firewall between users and the outside world. In an effort to increase security, many web links can be blocked, including Globus traffic. If you see a message that ends with “Details: 500 Command failed….”, then a firewall might be the cause.

**Uploading data from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](transferring-data-from-jgi.md) for instructions.

