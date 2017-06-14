1. Find the albums recorded by the artist Queen.

Album.where(artist_id: 51)

Album.where(artist_id: Artist.find_by(name: 'Queen').id)

2. Count how many tracks belong to the media type

"Protected MPEG-4 video file".
Track.where('media_type_id=?', MediaType.find_by(name: 'Protected MPEG-4 video file')).count
