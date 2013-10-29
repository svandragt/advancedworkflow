# Advanced Workflow Module

[![Build Status](https://secure.travis-ci.org/silverstripe-australia/advancedworkflow.png?branch=master)](http://travis-ci.org/australia/silverstripe-advancedworkflow)

Note: The SilverStripe 2.4 version of the module is available from the ss24
branch of the repository.

## Overview

A module that provides an action / transition approach to workflow, where a
single workflow process is split into multiple configurable states (Actions)
with multiple possible transitions between the actions.

Please see the wiki at [https://github.com/silverstripe-australia/advancedworkflow/wiki] 
for more info!

## Requirements

* SilverStripe 2.4+
* [Queued Jobs module][1] Required if you use the embargo/expiry functionality

## Installation

Add 

	SiteTree::add_extension('WorkflowApplicable');

to your site's _config.php file

To apply workflow to files, add this to _config.php:

	File::add_extension('FileWorkflowApplicable');

To enable embargo/expiry (scheduled publish/unpublish), use this:

	SiteTree::add_extension('WorkflowEmbargoExpiryExtension');

Make sure the QueuedJobs module is installed and configured correctly - 
you should have a cronjob similar to the following in place

	*/1 * * * * cd  && sudo -u www php /var/www/framework/cli-script.php dev/tasks/ProcessJobQueueTask

This is an example only. The key is to run the task as the same user as the web server.

[1]:https://github.com/nyeholt/silverstripe-queuedjobs


## Contributing

### Translations

Translations of the natural language strings are managed through a third party translation interface, transifex.com. Newly added strings will be periodically uploaded there for translation, and any new translations will be merged back to the project source code.

Please use [https://www.transifex.com/projects/p/silverstripe-advancedworkflow](https://www.transifex.com/projects/p/silverstripe-advancedworkflow) to contribute translations, rather than sending pull requests with YAML files.