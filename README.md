# Preface #

This document describes the functionality provided by the xlr-xlr-plugin.

See the **[XL Release Documentation](https://docs.xebialabs.com/xl-release/index.html)** for background information on XL Release and release concepts.

# Overview #

The xlr-xlr-plugin is an XL Release plugin that allows you to:

  * Programmatically create a template and assign tags to it
  * Create and start another release from an existing release. So you can create a subrelease from a parent release
  * Programmatically delete phases in the current release

For XL Release version 4.8.x you'll need at least version 1.7.x of the plugin.
Any XL Release version before 4.8.x should use version 1.6.5 or lower of the plugin.

## Tasks ##
+ Create and Start SubRelease
  * `templateName`: Name of the template from which to create the subrelease (`string`) 
  * `releaseTitle`: Name of the subrelease (`string`)
  * `releaseDescription`: Description of the subrelease (`string`)
  * `variables`: Comma-separated key-value pairs for the values of variables required by the subrelease, e.g. var1=value1,var2=value2 (`string`)
  * `asynch`: If [false], the task will wait for the subrelease to finish
  * `gateTaskTitle`: Title of the gate task in this release that should wait for the subrelease to complete. Skipped if not specified (blank).

+ Create Template
  * `templateName`: Name of the template to create (`string`)
  * `tags`: Comma-separated list of tags to associate with this template e.g. tag1,tag2 (`string`)

+ Delete Phases
  * `phases`: Comma-separated list of names of phases in the current release to delete e.g. phase1,phase2 (`string`)
  * **This task requires XL Release 4.5.0 or higher**

+ Get Task ID
  *  `taskTitle`: Title of the task to get the id for (`string`)
  * **This task requires XL Release 4.5.0 or higher**

+ Get Tags
  * `tags`: A List of the current tags for the release

  ![GetTags](images/GetTags.png)
  
+ Add Tag
  * `newTag`: New tag to add to the list of tags for the release
  * `tags`: A List of the current tags for the release

  ![AddTag](images/AddTag.png)
  
+ Set Tags
  * `newTags`: A List of tags to replace the tag list with
  * `tags`: A list of the curretn tags for the release

  ![SetTags](images/SetTags.png)
  