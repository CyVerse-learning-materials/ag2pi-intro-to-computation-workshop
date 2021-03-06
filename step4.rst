.. include:: cyverse_rst_defined_substitutions.txt
.. include:: custom_urls.txt

|CyVerse_logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_


Managing your data in the cloud
-------------------------------

**Description:**

After you've become familiar with downloading data from NEON Data API, or from other resources on the internet, into your cloud instances, you're going to be in a situation where you need to move them and store them somewhere more permanently.

Its important to accept that many of these public data repositories are stable and that data will be available from them in the future.

This means that you **should not create copies of original data** unless you are in a situation where the data are very large and downloading them again is prohibitive of your time.

|connect_de|


..
	#### Comment: short text description goes here ####

----


*Setting up iCommands*
~~~~~~~~~~~~~~~~~~~~~~

|Data Store Guide|

CyVerse Data Store uses a platform called `iRODS <https://irods.org/>`_ to manage its data. iRODS has a command line application called `iCommands <https://docs.irods.org/4.2.8/icommands/user/>`_ for moving data over the terminal.

First, we need to initiate a connection to the CyVerse iRODS.

.. 	#### Comment: Step title should be descriptive (i.e. Cleaning Read data) ###


**1.** Launch a terminal in a VICE application

For example `Jupyter Lab <https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=91c72a5d-0ce9-484f-a1f1-feba4cab75a5&app-id=bc93504c-d584-11e9-8413-008cfa5ae621/>`_ :

|JupyterLabShell|

Or `RStudio <https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=97782f8c-8c6f-4969-8c4e-2dd9d5bf5f96&app-id=a8b21a2c-e6f4-11ea-844a-008cfa5ae621/>`_ :

|RStudioTerminal|

**2.** In the Terminal type in ``iinit``

   This should echo out a set of information in the terminal:

   .. code ::

      One or more fields in your iRODS environment file (irods_environment.json) are missing;
      please enter them.

      Enter the host name (DNS) of the server to connect to:


**3.** Enter in the following data for each field:

  .. code ::

    Enter the host name (DNS) of the server to connect to: data.cyverse.org
    Enter the port number: 1247
    Enter your irods user name: user_name
    Enter your irods zone: iplant
    Those values will be added to your environment file (for use by
    other iCommands) if the login succeeds.

    Enter your current iRODS password:

  - host name (DNS): ``data.cyverse.org``
  - port number: ``1247``
  - irods user name: ``<your CyVerse username>``
  - irods zone: ``iplant``
  - current iRODS password: ``<your current password>``

**4.** You should now be authenticated to the Data Store.

   To test, try typing ``ils``

   If you do not echo back anything, try Step 2. again

*Uploading with iCommands*
~~~~~~~~~~~~~~~~~~~~~~~~~~

**4.** Type in ``ils``

   .. code ::

      rstudio@a4bdcc31:~$ ils

      /iplant/home/username:
      C- /iplant/home/username/analyses
      C- /iplant/home/username/ag2pi_workshop

  You should now see the contents of your personal Data Store

**5.** Upload a single file to the Data Store using ``iput``

  Create a new file in RStudio and give it a name, e.g. ``test.R``

  You need to select the file you want to copy, and the location in the Data Store you want to copy it to.

  .. code ::

     iput -KPvf /home/rstudio/test.R /iplant/home/username/ag2pi_workshop/

This command will take a single file ``test.R`` and copy it from the container to the Data Store folder ``/iplant/home/username/ag2pi_workshop/``

The flags ``K``, ``P``, ``v``, and ``f`` are described in the help file.

**6.** Upload a folder with recursive sub-folders and files

   Create a new folder in RStudio, and then create a folder inside of it.

   Next, we want to upload an entire directory with many folders and files in it.

   .. code ::

      iput -KPbrvf /home/rstudio/ag2pi_workshop/folder1/ /iplant/home/<your-user-name>/ag2pi_workshop/

  I have added the flags ``b`` for bulk, and ``r`` for recursive to the ``iput`` command. This will upload the entire directory ``folder1`` to the data store.

**7.** The ``P`` flag for Progressive and ``v`` flag for verbose will echo out the progress of the upload until it completes.

  When it is complete, the terminal should be available again.

  To test whether your files are now in CyVerse try:

  .. code ::

    ils /iplant/home/<your-user-name>/ag2pi_workshop/

    # and then

    ils /iplant/home/<your-user-name>/ag2pi_workshop/folder1

  You should be able to see the contents of your directory in the Data Store

**8.** These files are now in your private user space. No one can see them, but if you did want to share them, you can do so by modifying their permissions directly in the Discovery Environment, as shown in `Step 1 <./step1.html>`_, or by using the following commands:

  .. code ::

     ichmod

Follow the instructions in the help menu to set the user privileges and ownership.

This example makes your data directory public on the internet as a read-only archive:

  .. code ::

     ichmod read anonymous /iplant/home/<your-user-name>/ag2pi_workshop

*Downloading with iCommands*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

It is also likely that you're going to download data from the Data Store into your running Apps

**9.** Use the ``ils`` command to look for some shared data in the Data Store

  .. code ::

     ils /iplant/home/username/ag2pi_workshop

**10.** Download a file using ``iget``

  .. code ::

     iget -KPvf /iplant/home/username/ag2pi_workshop/folder1

  This should download an Rmd file into your local instance (whatever current working directory you're in in terminal)

**11.** Download a directory using ``iget``

  .. code ::

     time iget -KPbvrf /iplant/home/username/ag2pi_workshop/folder1

  Here we're using the ``time`` flag to tell us how long the download takes


*Downloading with WebDav*
~~~~~~~~~~~~~~~~~~~~~~~~~

CyVerse Data Store also uses `WebDav <https://cyverse.atlassian.net/wiki/spaces/DS/pages/241869825/Using+WebDAV>`_, an https based protocol for read-only data downloads from the Data Store.

We can use ``wget`` or ``curl`` commands in the terminal to download files this way.

**12.** Download a directory using ``wget``

   .. code ::

      time wget -r -np -R "index.html*" --cut-dirs=3 https://data.cyverse.org/dav-anon/iplant/projects/ag2pi_workshop/


  again, we're using the ``time`` function to monitor the download speeds.

  We're also using some ``wget`` flags to just get the data and folders back from the Data Store.


----


----

**Fix or improve this documentation**

- Search for an answer:
  |CyVerse Learning Center|
- Ask us for help:
  click |Intercom| on the lower right-hand side of the page
- Report an issue or submit a change:
  |Github Repo Link|
- Send feedback: `learning@CyVerse.org <learning@CyVerse.org>`_

----

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

.. Comment: Place Images Below This Line
   use :width: to give a desired width for your image
   use :height: to give a desired height for your image
   replace the image name/location and URL if hyperlinked


 .. |Clickable hyperlinked image| image:: ./img/IMAGENAME.png
    :width: 500
    :height: 100
 .. _CyVerse logo: http://learning.cyverse.org/

 .. |Static image| image:: ./img/IMAGENAME.png
    :width: 25
    :height: 25



.. Comment: Place URLS Below This Line

   # Use this example to ensure that links open in new tabs, avoiding
   # forcing users to leave the document, and making it easy to update links
   # In a single place in this document

   .. |Substitution| raw:: html # Place this anywhere in the text you want a hyperlink

      <a href="REPLACE_THIS_WITH_URL" target="blank">Replace_with_text</a>


.. |Github Repo Link|  raw:: html

   <a href="https://github.com/rbartelme/ag2pi_workshop" target="blank">Github Repo Link</a>

.. |connect_de| image:: ./img/de/connect_cyverse.svg
    :width: 700

.. |RStudioTerminal| image:: ./img/RStudioTerminal.png
		:width: 700

.. |JupyterLabShell| image:: ./img/JupyterTerminal.png
		:width: 700
