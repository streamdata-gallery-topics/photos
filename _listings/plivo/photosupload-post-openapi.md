---
swagger: "2.0"
x-collection-name: Plivo
x-complete: 0
info:
  title: Codenvy Account API Post Photos Upload
  description: This is a new photo upload endpoint. It is currently in beta.nCreate
    a new photo on behalf of the user and upload a file.nfile parameter is passed
    in multipart/form-data, other parameters are passed as query parametrs or multipart/form-data.
  version: 1.0.0
host: /account
basePath: https://codenvy.com/api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /photos:
    post:
      summary: Post Photos
      description: Create a new photo on behalf of the user, and receive an upload
        key in exchange.
      operationId: create-a-new-photo-on-behalf-of-the-user-and-receive-an-upload-key-in-exchange
      x-api-path-slug: photos-post
      parameters:
      - in: query
        name: aperture
        description: Aperture value
      - in: query
        name: camera
        description: Make and model of the camera
      - in: query
        name: category
        description: A numerical ID for the Category of the photo
      - in: query
        name: description
        description: Description for the photo
      - in: query
        name: focal_length
        description: Focal length in millimetres, a string representing an integer
          value
      - in: query
        name: iso
        description: ISO value
      - in: query
        name: latitude
        description: Latitude, in decimal format
      - in: query
        name: lens
        description: Lens used to make this photo
      - in: query
        name: longitude
        description: Longitude, in decimal format
      - in: query
        name: name
        description: Title of the photo
      - in: query
        name: privacy
        description: Whether to hide the photo from the user profile on the website
      - in: query
        name: shutter_speed
        description: Shutter speed in seconds, represented by string containing a
          rational expression if the value is 1sec
      - in: query
        name: tags
        description: Comma-separated list of tags to apply to the photo
      responses:
        200:
          description: OK
      tags:
      - Photos
  /photos/:id:
    put:
      summary: Put Photos
      description: 'Allows the client application to update user-editable information
        on a photo.nnnResource URLnnhttps://api.500px.com/v1/photos/:idnnnnAuthenticationnnRequired;
        OAuth. The client application must use the OAuth access token issued for the
        owner of the photo to access this resouce.nnnParametersnnThe application must
        provide the ID of the photo to update in the URL of the request. The following
        parameters are recognized when included in the query string or POST body:nnnnname:
        Title of the photo, up to 255 characters in length.nndescription: Text description
        of the photo, up to 65535 characters in length.nncategory: Integer number
        of the category of the photo. See category mapping for exact values.nntags:
        Comma-separated list of tags applicable to this photo.nnadd_tags: Comma-separated
        list of tags to add to this photos existing tags.nnremove_tags: Comma-separated
        list of tags to remove from this photos existing tags.nnshutter_speed: Shutter
        speed value for the photo, internally stored as string.nnfocal_length: Focal
        length value for the photo, internally stored as string.nnaperture: Aperture
        value value for the photo, internally stored as string.nniso: Integer ISO
        value for the photo.nncamera: Make and model of the camera used to take this
        photo.nnlens: Information about the lens used to take this photo.nnlatitude:
        Latitude of the location this photo was taken at represented by a decimal
        number.nnlongitude: Longitude of the location this photo was taken at represented
        by a decimal number.nnnsfw: Boolean value indicating that the photo may contain
        not-safe-for-work content or content not suitable for minors.nnlicense_type:
        Integer number of the license type chosen for this photo. See license type
        mapping for exact values.nnprivacy: Integer value indicating that the photo
        should be shown (0) or hidden (1) on the users profile.nncrop: A hash containing
        keys x, x2, y, y2 and representing coordinates within which the thumbnail
        must be cropped. The crop is made using the top left corner as the origin.
        The points must be given relative to image size 4, an image of at most 900px
        on the larger side. The client application may skip this if the user does
        not wish to change photo thumbnail.nnnnImplementation detailsnnA parameter
        missing from the request will not be updated.  A parameter set to an empty
        string or null value will be interpreted as the user wishing to reset the
        value of the field to its default value.nnYou can use the add_tags and remove_tags
        parameters to manupulate a photos tags without having to send the complete
        list of tags in the request.nnnReturn formatnnA JSON object containing key
        photo, where photo is a Photo object in full format.nnnErrorsnnAll known errors
        cause the resource to return HTTP error code header together with a JSON array
        containing at least status and error keys describing the source of error.nnnn401:
        Invalid OAuth request: The request was refused because the OAuth signature
        is incorrect.nn404: Photo with ID not found: The photo ID provided is not
        known to the system.nn404: Photo with ID has been deleted: The photo has been
        deleted and can not be edited.nn404: Photo with ID belongs to a deactivated
        user: The photo belongs to a user that is no longer active and can not be
        edited.nn400: Bad photo category: An unrecognized photo category value has
        been provided.nn400: Bad license type: An unrecognized license type value
        has been provided.'
      operationId: allows-the-client-application-to-update-usereditable-information-on-a-photoresource-urlhttpsapi500px
      x-api-path-slug: photosid-put
      parameters:
      - in: query
        name: 'add_tags: Comma-separated list of tags to add to this photos existing
          tags.'
      - in: query
        name: 'aperture: Aperture value value for the photo, internally stored as
          string.'
      - in: query
        name: 'camera: Make and model of the camera used to take this photo.'
      - in: query
        name: 'category: Integer number of the category of the photo. See category
          mapping for exact values.'
      - in: query
        name: 'crop: A hash containing keys x, x2, y, y2 and representing coordinates
          within which the thumbnail must be cropped. The crop is made using the top
          left corner as the origin. The points must be given relative to image size
          4, an image of at most 900px'
      - in: query
        name: 'description: Text description of the photo, up to 65535 characters
          in length.'
      - in: query
        name: 'focal_length: Focal length value for the photo, internally stored as
          string.'
      - in: query
        name: 'iso: Integer ISO value for the photo.'
      - in: query
        name: 'latitude: Latitude of the location this photo was taken at represented
          by a decimal number.'
      - in: query
        name: 'lens: Information about the lens used to take this photo.'
      - in: query
        name: 'license_type: Integer number of the license type chosen for this photo.
          See license type mapping for exact values.'
      - in: query
        name: 'longitude: Longitude of the location this photo was taken at represented
          by a decimal number.'
      - in: query
        name: 'name: Title of the photo, up to 255 characters in length.'
      - in: query
        name: 'nsfw: Boolean value indicating that the photo may contain not-safe-for-work
          content or content not suitable for minors.'
      - in: query
        name: 'privacy: Integer value indicating that the photo should be shown (0)
          or hidden (1) on the users profile.'
      - in: query
        name: 'remove_tags: Comma-separated list of tags to remove from this photos
          existing tags.'
      - in: query
        name: 'shutter_speed: Shutter speed value for the photo, internally stored
          as string.'
      - in: query
        name: 'tags: Comma-separated list of tags applicable to this photo.'
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
  /photos/:id/comments:
    post:
      summary: Post Photos Comments
      description: Creates a new comment for the photo.
      operationId: creates-a-new-comment-for-the-photo
      x-api-path-slug: photosidcomments-post
      parameters:
      - in: query
        name: body (required)
        description: Content of the comment
      - in: query
        name: id (required)
        description: The Photo ID to post comments for
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Comments
  /photos/:id/favorite:
    post:
      summary: Post Photos Favorite
      description: Adds the photo to users list of favorites.
      operationId: adds-the-photo-to-users-list-of-favorites
      x-api-path-slug: photosidfavorite-post
      parameters:
      - in: query
        name: id (required)
        description: ID of the photo the favorite is cast upon
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Favorite
  /photos/:id/favorites:
    get:
      summary: Get Photos Favorites
      description: Returns all users that had favorite that photo.
      operationId: returns-all-users-that-had-favorite-that-photo
      x-api-path-slug: photosidfavorites-get
      parameters:
      - in: query
        name: page
        description: Return a specific page in the photo stream
      - in: query
        name: rpp
        description: The number of results to return
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Favorites
  /photos/:id/report:
    post:
      summary: Post Photos Report
      description: Allows to report a photo.
      operationId: allows-to-report-a-photo
      x-api-path-slug: photosidreport-post
      parameters:
      - in: query
        name: id (required)
        description: ID of the photo to report
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Report
  /photos/:id/tags:
    post:
      summary: Post Photos Tags
      description: Adds tags to the photo. Accepts one or multiple coma separated
        tags.
      operationId: adds-tags-to-the-photo-accepts-one-or-multiple-coma-separated-tags
      x-api-path-slug: photosidtags-post
      parameters:
      - in: query
        name: id (required)
        description: The Photo ID to add tags for
      - in: query
        name: tags (required)
        description: Coma separated tags
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Tags
  /photos/:id/vote:
    post:
      summary: Post Photos Vote
      description: Allows the user to vote for a photo.
      operationId: allows-the-user-to-vote-for-a-photo
      x-api-path-slug: photosidvote-post
      parameters:
      - in: query
        name: id (required)
        description: ID of the photo the vote is cast upon
      - in: query
        name: vote (required)
        description: 'vote, values: 0 for dislike or 1 for like'
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Vote
  /photos/:id/votes:
    get:
      summary: Get Photos Votes
      description: Returns all users that had liked this photo.
      operationId: returns-all-users-that-had-liked-this-photo
      x-api-path-slug: photosidvotes-get
      parameters:
      - in: query
        name: page
        description: Return a specific page in the photo stream
      - in: query
        name: rpp
        description: The number of results to return
      responses:
        200:
          description: OK
      tags:
      - Photos
      - :id
      - Votes
  /photos/search:
    get:
      summary: Get Photos Search
      description: Returns a listing of twenty (up to one hundred) photos from search
        results for a specified tag, keyword, or location.
      operationId: returns-a-listing-of-twenty-up-to-one-hundred-photos-from-search-results-for-a-specified-tag-keyword
      x-api-path-slug: photossearch-get
      parameters:
      - in: query
        name: comments_count u2014u00a0Sort by the number of comments, most commented
          first.
      - in: query
        name: created_at
        description: 'Default: sort by time of upload, most recent first'
      - in: query
        name: exclude
        description: String name of the category to exclude from the results
      - in: query
        name: favorites_count
        description: Sort by the number of favorites, most favorited first
      - in: query
        name: geo
        description: A geo-location point of the format latitude,longitude,radius&lt;units&gt;
      - in: query
        name: highest_rating
        description: Sort by highest rating achieved, highest rated first
      - in: query
        name: image_size
        description: The photo size to be returned
      - in: query
        name: 'license_type -- Restrict the results to one or more license types.  Multiple
          types can be separated with a comma: license_type=1,4.'
      - in: query
        name: only
        description: String name of the category to return photos from
      - in: query
        name: page
        description: Return a specific page
      - in: query
        name: rating
        description: Sort by current rating, highest rated first
      - in: query
        name: rpp
        description: The number of results to return
      - in: query
        name: sort u2014u00a0Sort photos in the specified order. The following values
          are recognized:nnnn_score
        description: Sort by query score, best match first
      - in: query
        name: tag
        description: A complete tag string to search for
      - in: query
        name: tags
        description: Returns an array of tags for each photo
      - in: query
        name: taken_at u2014u00a0Sort by the original date of the image extracted
          from metadata, most recent first (might not be available for all images).
      - in: query
        name: term
        description: A keyword to search for
      - in: query
        name: times_viewed u2014u00a0Sort by the number of views, most viewed first.
      - in: query
        name: votes_count u2013 Sort by the number of votes, most voted on first.
      responses:
        200:
          description: OK
      tags:
      - Photos
      - Search
  /photos/upload:
    post:
      summary: Post Photos Upload
      description: This is a new photo upload endpoint. It is currently in beta.nCreate
        a new photo on behalf of the user and upload a file.nfile parameter is passed
        in multipart/form-data, other parameters are passed as query parametrs or
        multipart/form-data.
      operationId: this-is-a-new-photo-upload-endpoint-it-is-currently-in-betacreate-a-new-photo-on-behalf-of-the-user-
      x-api-path-slug: photosupload-post
      parameters:
      - in: query
        name: aperture
        description: Aperture value
      - in: query
        name: camera
        description: Make and model of the camera
      - in: query
        name: category
        description: A numerical ID for the Category of the photo
      - in: query
        name: description
        description: Description for the photo
      - in: query
        name: file (required)  - Photo filename in JPG/JPEG, passed along with multipart/form-data.
      - in: query
        name: focal_length
        description: Focal length in millimetres, a string representing an integer
          value
      - in: query
        name: iso
        description: ISO value
      - in: query
        name: latitude
        description: Latitude, in decimal format
      - in: query
        name: lens
        description: Lens used to make this photo
      - in: query
        name: longitude
        description: Longitude, in decimal format
      - in: query
        name: name
        description: Title of the photo
      - in: query
        name: privacy
        description: Whether to hide the photo from the user profile on the website
      - in: query
        name: shutter_speed
        description: Shutter speed in seconds, represented by string containing a
          rational expression if the value is 1sec
      responses:
        200:
          description: OK
      tags:
      - Photos
      - Upload
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---