# Amazon S3
  We utilize amazon S3 to store data for a few of our applications.  PDC describe store information for both the short term (pre-curation) and langer term (post curation) in Amazon S3 buckets.  There is also a legacy S3 storage bucket for our dspace instance.

  ## Amazon S3 Backup
  
  The statement below is copied directly from Amazon.
    [Amazon S3 is designed for 99.999999999%](https://aws.amazon.com/pm/serv-s3/?trk=20e04791-939c-4db9-8964-ee54c41bc6ad&sc_channel=ps&ef_id=CjwKCAjw6p-oBhAYEiwAgg2Pgkrw28VJ26x_EVwAskGLKsYWZeGUIj8rYntJjIw8e6rgJQ2b8ILSwxoCs8MQAvD_BwE:G:s&s_kwcid=AL!4422!3!651751060941!p!!g!!amazon%20s3%20cloud%20storage!19852662362!145019202897)
 (11 9's) of durability, and stores data for millions of customers all around the world.

 We therefore do not need to worry about backing up our short to medium term data in another location.

 For longer term preservation we are...

 ## Versioning Amazon S3

 In addition to the fact that amazon promises to preserve the data we have [turned on versioning](https://github.com/pulibrary/rdss-handbook/blob/main/globus.md#making-a-new-s3-bucket) (see step 9) in our s3 buckets for PDC describe.  This allows us to recover from accidental deletions of data, by either the system or a human, that are discovered within 30 days.