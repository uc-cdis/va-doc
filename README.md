# How to Generate Documentation for VA data commons

## Overview

Documentation for VA is usually written in a markdown or google drive file. The steps of converting markdown/google drive/word/etc files to HTML is currently as folows.

1. Convert documentation into markdown format if its not currently in markdown format
2. Convert markdown to rst format via pandocs
3. Convert rst to HTML via sphinx

## Setup

* Please follow [instructions](https://pandoc.org/installing.html) and install pandocs 
* Please follow [instructions](https://www.sphinx-doc.org/en/master/usage/installation.html) and install sphinx

## Steps

1. Please save the documentation in markdown format to **va-doc/docs/source/index.md**
2. Run the following command to convert **index.md** to and rst file **index.rst** ```pandoc index.md --from markdown --to rst -s -o index.rst```
3. Now naviagte to **va-doc/docs** and run the following to convert rst file to HTML ```sphinx-build -b html source build```
4. Now all the resulting HTML files will be stored to **va-doc/docs/build**
5. You can open up **va-doc/docs/build/index.html** to check that the HTML generated looks correct

## Adding generated documentation to qa/preprod/prod

1. Navigate to the corosponding manifest repo. [here](https://github.com/uc-cdis/gitops-qa) for qa and [here](https://github.com/uc-cdis/cdis-manifest) for preprod/prod
2. Go to the corosponding documentation repo for the data commons we're updating documentation for. Example: for preprod this would be **va-testing.data-commons.org/dashboard/Public/documentation**
3. Remove all current files in there via ```rm -rf *```
4. Now copy all files from **va-doc/docs/build** into the documentation directory
5. Merge the changes into master
6. Hop into the corosponding enviorment and run ```gen3 dashboard gitops-sync``` for documentation to be uploaded.
7. Reroll portal via ```gen3 kube-setup-portal``` to reroll portal and documentations to be viewable via portal 
