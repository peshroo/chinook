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

5. Find the total amount of time required to listen to all the tracks in the database.

Track.sum('Milliseconds')

6. Find the highest price of any track that has the media type "MPEG audio file".

Track.maximum(:unit_price).where('media_type_id=?', MediaType.find_by(name: 'Protected MPEG-4 video file'))

MediaType.where(name: ‘MPEG audio file’)
  Track.where(media_type_id: 1).maximum(:unit_price)

7. Find the name of the most expensive track that has the media type "MPEG audio file".

Track.where('media_type_id=?', MediaType.find_by(name: 'MPEG audio file')).maximum(:unit_price)     .name

Track.where('media_type_id=?', MediaType.find_by(name: 'MPEG audio file')).order(unit_price: :desc).first.name

8. Find the 2 oldest artists.

Artist.order(created_at: :asc).limit(2)
