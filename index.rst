.. include:: cyverse_rst_defined_substitutions.txt
.. include:: custom_urls.txt

|CyVerse_logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

**AG2PI Foundations of Computation: An Introduction for Biologists Workshop**
============================================================================

**Times: 11:00 - 16:00 EST/08:00-13:00 PST**

**Dates: Tuesday 19th, Thursday 21st, and Friday 22nd January 2021**

**Ready to join the workshop? Follow these steps:**

**Step 1: Create CyVerse Account (free)** |CyVerse User Portal|

Please use your institutional email address, and if you don't have an |ORCID ID| - sign up for one of those too, they're super important and valuable!

**Step 2: Sign up for Workshop** |Workshop Enrollment|

**Step 3: Review this website -- all of our training materials will be posted or linked from here**

..
    #### Comment: Use short, imperative titles e.g. Upload and share data, uploading and
    sharing data ####

Goal
----

The goals of the workshop are to allow you as new data scientists to leave with an understanding of using CyVerse resources, the command line, and the basics of R and Rstudio programming.

You will have opportunities to work in your preferred Integrated Development Environment (IDE) in the public research cyberinfrastructure. CyVerse enables us to work with large and very large analyses.


..
    #### Comment: Avoid covering upstream and downstream steps that are not explicitly and
    necessarily part of the tutorial - write or link to separate quick
    starts/tutorials for those parts ####

----

Tutorial Maintainer(s)
------------------------

Who to contact if this guide needs fixing.

.. list-table::
    :header-rows: 1

    * - Maintainer
      - Institution
      - GitHub Username
    * - Ryan Bartelme
      - CyVerse / University of Arizona
      - ``rbartelme``
    * - Tyson Swetnam
      - CyVerse / University of Arizona
      - ``tyson-swetnam``
----

Content Links
-------------

Use the table of contents on the left side of the page to navigate

.. toctree::
	:maxdepth: 2

	Home <self>
  Code of Conduct <code_of_conduct.rst>
  Agenda <agenda.rst>
  Discovery Environment Overview <step1.rst>
  Visual Interactive Computing <step2.rst>
  Managing data in the cloud <step4.rst>
  Data Science Workspaces <step6.rst>
  Introducing the Shell <step7.rst>
  Introducing R and Rstudio <step8.rst>
..
	#### Comment:This tutorial can have multiple pages. The table of contents assumes
	you have an additional page called 'Step One' with content located in 'step1.rst'
	Edit these titles and filenames as needed ####


Prerequisites
-------------

Downloads, access, and services
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

*In order to complete this tutorial you will need access to the following services/software*

..
	#### comment: delete any row not needed in this table ####

.. list-table::
    :header-rows: 1

    * - Prerequisite
      - Preparation/Notes
      - Link/Download
    * - |CyVerse_globe|_
      - You will need a CyVerse account to use our tools
      - |CyVerse User Portal|
    * - |cyberduck|_
      - CyberDuck File manager (Windows and Mac OS X only)
      - |Download Cyberduck|

Platform(s)
~~~~~~~~~~~

We provide ready-to-use examples of (1) Docker containers with pre-configured  software development environments, (2) Example datasets,  & (3) ReadTheDocs style documentation that will allow for self-paced asynchonous learning as well as opportunities for in-person live coding.

*We will use the following CyVerse platform(s):*

 ..
   #### comment: delete any row not needed in this table ####

.. list-table::
    :header-rows: 1

    * - Platform
      - Interface
      - Link
      - Platform Tour
    * - Data Store
      - GUI/Command line
      - |Data Store|
      - |Data Store Guide|
    * - Discovery Environment
      - Web/Point-and-click
      - |Discovery Environment|
      - |Discovery Environment Guide|
    * - Learning Center
      - ReadTheDocs
      - This website
      - |CyVerse Learning Center|

Application(s) used
~~~~~~~~~~~~~~~~~~~
..
	#### Comment: need to update CyVerse Links ####

**Discovery Environment App(s):**

.. list-table::
    :header-rows: 1

    * - App name
      - Version
      - Description
      - Quick Launch
      - GitHub repositories
    * - Workspace
      - ``latest``
      - |all-the-things|
      -	|workspace-geospatial-latest|_
      - |CyVerse Workspace GitHub|
    * - RStudio
      - ``3.6.3``
      - Rocker Project RStudio with Tidyverse applications pre-installed
      - |rstudio-verse|_
      - |CyVerse R Studio GitHub|


Input and example data
~~~~~~~~~~~~~~~~~~~~~~

*In order to complete this tutorial you will need to have the following inputs prepared*

..
	#### comment: update with example dataset ####

.. list-table::
    :header-rows: 1

    * - Input File(s)
      - Format
      - Preparation/Notes
      - Example Data
    * - Sample Datasets
      - various
      - Example datasets cached on the CyVerse Data Store
      - |WebDav|

----

**Fix or improve this documentation**

- Search for an answer:
  |CyVerse Learning Center|
- Ask us for help:
  click |Intercom| on the lower right-hand side of the page
- Report an issue or submit a change:
  |Github Repo Link|
- Send feedback: `learning@CyVerse.org <learning@CyVerse.org>`_

.. comment:

   Uncomment the below and fix with this repo's information if citing

   **Citation**

   You may cite this work as:
   [Repository Title]
   [Author(s)]
   [Repository Release Version]
   [DOI: Zenodo DOI link (generated from Github Release/Zenodo)]
----

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`__


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

.. |Workshop Enrollment|  raw:: html

   <a href="https://user.cyverse.org/workshops/59/overview" target="blank">Workshop Enrollment</a>

.. |CyVerse R Studio GitHub|  raw:: html

   <a href="https://github.com/cyverse-vice/rstudio-verse" target="blank">CyVerse RStudio GitHub</a>


.. |CyVerse JupyterLab GitHub|  raw:: html

   <a href="https://github.com/cyverse-vice/jupyterlab-datascience" target="blank">CyVerse JupyterLab GitHub</a>

.. |Download Cyberduck|  raw:: html

   <a href="https://cyberduck.io/" target="blank">Download Cyberduck</a>

.. |Github Repo Link|  raw:: html

   <a href="https://github.com/rbartelme/ag2pi_workshop" target="blank">Github Repo Link</a>

.. |all-the-things| image:: ./img/all-the-things.png
    :width: 400

.. |cyberduck| image:: ./img/cyberduck.png
    :width: 50

.. _cyberduck: https://cyberduck.io

.. |github| image:: ./img/github.png
    :width: 50

.. _github: https://github.com

.. |gee| image:: ./img/gee.png
    :width: 50

.. _gee: https://earthengine.google.com

.. |GitHub| raw:: html

   <a href="https://github.com" target="blank">GitHub</a>

.. |GEE| raw:: html

   <a href="https://earthengine.google.com/" target="blank">GEE</a>

.. |WebDav| raw:: html

   <a href="https://data.cyverse.org/dav-anon/iplant/projects/NEON_workshop" target="blank">WebDav</a>
