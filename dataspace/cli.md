# DSpace Command-Line Interface (CLI)

## Usage

### Workflow Management

#### Refreshing Task Pools for Users in Groups

There is a known bug in DSpace 5.5 that causes users who are newly added to Groups not to be able to see or interact with tasks in the workflow pool associated with that Group in their dashboard when they log in.

In order to address this, manual intervention is needed. Over on [dspace-cli](https://github.com/pulibrary/dspace-cli), the following commands must be executed to accomplish this:

```jruby
java_import(org.dspace.eperson.Group)
java_import(org.dspace.workflow.WorkflowItem)
java_import(org.dspace.workflow.WorkflowManager)
java_import(org.dspace.eperson.EPerson)

group = Group.findByName(DSpace.context, $GROUP_NAME)
members = Group.allMembers(DSpace.context, group)
eperson = Java::OrgDspaceEperson::EPerson.findByEmail(DSpace.context, $USER_ALREADY_IN_GROUP)

workflow_items = Java::OrgDspaceWorkflow::WorkflowManager.getPooledTasks(DSpace.context, eperson)
pool_items = workflow_items.to_a.map { |wfi| wfi.getItem }
pool_items.map { |item| item.getID }
items = pool_items.map { |item| DSpace::CLI::Item.new(item) }
items.each { |i| i.workflow_item.add_task_pool_user($USER_NEW_TO_GROUP) }
```

Where the variables in the above example are populated with values as follows:

- `$GROUP_NAME` is a quoted string of the name of the DataSpace group to which the user has been newly added (example: `"Lib_DigPubs_Reviewers"`).
- `$USER_ALREADY_IN_GROUP` is the email address associated with a user already in the `$GROUP_NAME` group before the tasks that need to be visible were created.
- `$USER_NEW_TO_GROUP` is the email address associated with the user who is newly associated with the `$GROUP_NAME` group, and needs to have the group’s tasks that are currently in the group’s workflow pool become visible to them.

Once the `items.each` loop at the bottom of the code block above completes, the change should be immediately visible in the DataSpace interface.