# Welcome to Learning with Astra #

If you have attended recently our workshops here, we ask you to create your own Github repo showing off your learning journey with Astra. You could use this repo here as a start: fork it and update it with your own examples.

## Explain your use case ##

Pick an example application that you could see on Astra and describe the entities and queries for it. 

Include diagrams, screenshots etc to make it more interesting and better convey your ideas.

## Create your own tables on Astra ##

Example tables that we used in the workshop:

```
CREATE TABLE IF NOT EXISTS comments_by_user (
    userid uuid,
    commentid timeuuid,
    videoid uuid,
    comment text,
    PRIMARY KEY ((userid), commentid)
) WITH CLUSTERING ORDER BY (commentid DESC);

CREATE TABLE IF NOT EXISTS comments_by_video (
    videoid   uuid,
    commentid timeuuid,
    userid    uuid,
    comment   text,
    PRIMARY KEY ((videoid), commentid)
) WITH CLUSTERING ORDER BY (commentid DESC);
```

Show us your own tables - for the data model of your choice.

```
spacecraft_journey_catalog     spacecraft_temperature_over_time
spacecraft_pressure_over_time  spacecraft_location_over_time   
comments_by_user               comments_by_video               
spacecraft_speed_over_time   
```

## Insert some data ##

Here some example data that we used in the workshop:

```
INSERT INTO comments_by_user (userid, commentid, videoid, comment)
VALUES (11111111-1111-1111-1111-111111111111, NOW(), 12345678-1234-1111-1111-111111111111, 'I keep watching this video');

INSERT INTO comments_by_user (userid, commentid, videoid, comment)
VALUES (11111111-1111-1111-1111-111111111111, NOW(), 12345678-1234-1111-1111-111111111111, 'Soo many comments for the same video');
```

Show off your own data inserts, into your own tables:

```
Your data goes here
```

Now show the output, for example:

```
select * from comments_by_user;

 userid                               | commentid                            | comment                              | videoid
--------------------------------------+--------------------------------------+--------------------------------------+--------------------------------------
 11111111-1111-1111-1111-111111111111 | 5e58bcc0-08c7-11eb-b6d0-2f7e43d4e9e5 | Soo many comments for the same video | 12345678-1234-1111-1111-111111111111
 11111111-1111-1111-1111-111111111111 | 5def4c90-08c7-11eb-b6d0-2f7e43d4e9e5 |           I keep watching this video | 12345678-1234-1111-1111-111111111111
...
...
...
```

Include some screenshots!

## Experiment with CRUD and show the outputs: ##

Examples from the workshop:

```
UPDATE comments_by_video 
SET comment = 'This is fun!' 
WHERE videoid = 12345678-1234-1111-1111-111111111111 AND commentid = 494a3f00-e966-11ea-84bf-83e48ffdc8ac;

SELECT * FROM comments_by_video;
```

```
DELETE FROM comments_by_video 
WHERE videoid = 12345678-1234-1111-1111-111111111111 AND commentid = 494a3f00-e966-11ea-84bf-83e48ffdc8ac;

SELECT * FROM comments_by_video;
```

Show us something similar with your own tables.

Try something different:

Check out the CQL reference and try commands that we did not use in the workshop:

https://docs.datastax.com/en/cql-oss/3.3/cql/cql_reference/cqlReferenceTOC.html

Let us know what you find:

```
update comments_by_user set comment = 'This is new valu e for comment' where commentid = 5def4c90-08c7 =  11111111-1111-1111-1111-111111111111;


token@cqlsh:spacecraft> select * from comments_by_user 
              ... ;

 userid                               | commentid                            | comment                              | videoid
--------------------------------------+--------------------------------------+--------------------------------------+--------------------------------------
 11111111-1111-1111-1111-111111111111 | 5e58bcc0-08c7-11eb-b6d0-2f7e43d4e9e5 | Soo many comments for the same video | 12345678-1234-1111-1111-111111111111
 11111111-1111-1111-1111-111111111111 | 5def4c90-08c7-11eb-b6d0-2f7e43d4e9e5 |       This is new valu e for comment | 12345678-1234-1111-1111-111111111111
```

Or connect, read and write to your Astra database via other methods.

Tell us how you do it, we would love to know. 

```
Show your connection code
```

The starry sky is the limit: Build your own app with Astra and show it off for a chance to have it included with our Sample Galleries



