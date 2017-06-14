1. Find the albums recorded by the artist Queen.

Album.where(artist_id: 51)

Album.where(artist_id: Artist.find_by(name: 'Queen').id)
