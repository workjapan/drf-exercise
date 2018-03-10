#  DRF Exercise

This is a simple SRF exercise that requires you to build a database and an API on top of the provided dataset.

## Data Details

 - Inside `./data` directory, you'll find a file named `lastfm_subset.zip` which contains a subset of music data from last.fm
 - The data is divided inside directories created based on the song ID
 - Each JSON document has data for a single song. Following data belongs in the `/B/G/W/TRBGWVI128E0788AE7.json` file.

```
{
  "artist": "22-20s",  // Artist name
  "timestamp": "2011-08-16 01:35:22.887609",
  "similars": [
    [
      "TRBNUEO128E0788AE6",     // <-- Similar Song ID
      1                         // <-- similarity score
    ],
    [
      "TRTKZIA128E0788AE5",     // <-- Similar Song ID
      0.97458800000000001       // <-- similarity score
    ],
    ...
  ],
  "tags": [
    [
      "indie",      // <-- Tag name
      "100"         // <-- confidence score
    ],
    [
      "rock",
      "75"
    ],
    [
      "good conservatism",
      "25"
    ],
    ...
  ],
  "track_id": "TRBGWVI128E0788AE7",  // Song ID
  "title": "Hold On"
}
```

## Task Details

 - You need to design a DB Schema based on this data and then import this json dataset into the DB.
 - That includes creating the entities and the relationship between them so that they can be queried accordingly.
 - E.g. you should be able to find all songs belonging to a certain tag. (Additional points if you can sort by the confidence. Each tag for a song has an integer beside it, that shows the confidence of that song being relating to that tag. E.g. The above song is more indie than rock)
 - You may use any RDBMS, but Postgres is preferred.
 - After the data is imported, you need to build an API on top of it using Django REST Framework.
   - Endpoint to list all entities
   - Endpoint to list related songs for a given song, sorted accordingly
   - Endpoint to list all songs for a given tag
   - Endpoint to search for songs
   - Endpoint to search for artist
   - Endpoint to list all songs for a given artist
 - Open API without any authentication is fine. If you feel like doing it, add token based authentication.
 - Follow standard REST architecture for url structure and API design.
 - Follow PEP8.
 - Either Python 2.7.x or 3.6 is fine. 3.6 is preferred.
 - You can create a github repo and push the code there and then share the repo url, and add [@iambibhas](https://github.com/iambibhas) as a collaborator so that I receive the notification.

## Assessment

 - Document how you imported the data. Add the data import script(s) in the repo, preferably as a management command.
 - You can either run the application locally and use something like `ngrok` to demo it, or include the db dump so that we can import the dump to our local db and run our own local server based on your code. (`./manage.py runserver`)
 - Clean readable code is preferred over a feature rich app.