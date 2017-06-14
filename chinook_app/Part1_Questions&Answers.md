1. Find the albums recorded by the artist Queen.

Album.where(artist_id: 51)

Album.where(artist_id: Artist.find_by(name: 'Queen').id)

2. Count how many tracks belong to the media type

"Protected MPEG-4 video file".
Track.where('media_type_id=?', MediaType.find_by(name: 'Protected MPEG-4 video file')).count

3. Find the genre with the name "Hip Hop/Rap".

Genre.where('name = ?', "Hip Hop/Rap")

4. Count how many tracks belong to the "Hip Hop/Rap" genre

Track.where('genre_id = ?', Genre.find_by(name: 'Hip Hop/Rap')).count
