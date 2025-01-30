# 🎵 Music App

## Description

This project aims to build a music app that allows both **Admin** and **End-users** to manage and interact with music data. The app will include functionality for users to register and log in, manage music content such as artists, albums, tracks, and playlists, and implement a favorites system. The backend is built using **Golang**, **Gin framework**, and **MySQL**.

---

## 🛠️ Technologies

- **Gin framework** for fast and efficient web routing
- **SQLx** or **Gorm** for ORM and database interaction
- **JWT** for secure user authentication and authorization
- **MySQL** for relational database management

---

## 👥 Users

The application supports two types of users:

- **Admin**: Full access to all features, including the ability to modify content.
- **User**: Limited to viewing content but can favorite or unfavorite tracks.

> **Note:** Admin users are essentially users too. They can access all functionalities of a regular user but with additional permissions to manage content.

---

## 📚 Models

### 1. **Artist**
Represents the artist who creates the music.
- `id`: Unique identifier
- `name`: Name of the artist
- `image_url`: URL to artist's image
- `created_at`: Timestamp when the artist was created
- `updated_at`: Timestamp when the artist was last updated

### 2. **Album**
An album created by an artist containing multiple tracks.
- `id`: Unique identifier
- `name`: Name of the album
- `description`: Short description of the album
- `image_url`: URL to album cover
- `published_at`: Date when the album was published
- `is_published`: Boolean flag indicating if the album is published
- `artist_id`: Foreign key linking to the artist
- `created_at`: Timestamp when the album was created
- `updated_at`: Timestamp when the album was last updated

### 3. **Track**
Represents an individual music track in an album or playlist.
- `id`: Unique identifier
- `name`: Name of the track
- `index`: Track position in the album
- `track_url`: URL to the track file
- `image_url`: URL to track's album cover image
- `album_id`: Foreign key linking to the album
- `is_published`: Boolean flag indicating if the track is published
- `created_at`: Timestamp when the track was created
- `updated_at`: Timestamp when the track was last updated

### 4. **Playlist**
A collection of tracks curated by the user or admin.
- `id`: Unique identifier
- `name`: Name of the playlist
- `description`: Playlist description
- `image_url`: URL to playlist cover image
- `is_published`: Boolean flag indicating if the playlist is published
- `created_at`: Timestamp when the playlist was created
- `updated_at`: Timestamp when the playlist was last updated

### 5. **Favourite Tracks**
A collection representing tracks favorited by users.
- `id`: Unique identifier
- `track_id`: Foreign key linking to the track
- `user_id`: Foreign key linking to the user
- `index`: Position of the track in the favorites list

---

## 🔒 Authentication APIs

### Admin Authentication
- **Admin Register**: Register a new admin user.
- **Admin Login**: Log in an admin user and receive a JWT token.

### User Authentication
- **User Register**: Register a new user.
- **User Login**: Log in a user and receive a JWT token.

---

## 🛠️ Admin Functionality APIs

These APIs are available only to admins:

- **Create Artist**: Add a new artist to the platform.
- **Read Artist**: Fetch details of an artist.
- **Update Artist**: Modify an existing artist.
- **Delete Artist**: Remove an artist from the platform.

- **Create Album**: Add a new album under an artist.
- **Read Album**: Fetch album details.
- **Update Album**: Modify an album.
- **Delete Album**: Remove an album from the platform.

- **Create Track**: Add a new track to the platform.
- **Read Track**: Fetch track details.
- **Update Track**: Modify an existing track.
- **Delete Track**: Remove a track.

- **Add Track to Album**: Assign tracks to an album.
- **Remove Track from Album**: Remove tracks from an album.

- **Create Playlist**: Add a new playlist to the platform.
- **Read Playlist**: Fetch playlist details.
- **Update Playlist**: Modify an existing playlist.
- **Delete Playlist**: Remove a playlist from the platform.

- **Add Track to Playlist**: Add tracks to a playlist.
- **Remove Track from Playlist**: Remove tracks from a playlist.

- **Get Playlists**: List all playlists.
- **Get Playlist by ID**: Fetch a specific playlist and its tracks by ID.

---

## 👥 User Functionality APIs

These APIs are available to regular users:

- **Fetch All Albums**: Retrieve a list of all available albums.
- **Fetch All Tracks**: Retrieve a list of all tracks available in the app.
- **Fetch Tracks by Album ID**: Retrieve tracks for a specific album by ID.
- **Get Playlists**: Retrieve all playlists available.
- **Get Playlist by ID**: Fetch a playlist and its tracks by ID.

- **Favourite/Unfavourite Track**: Mark a track as favorite or unfavorite.
- **Get Favourite Tracks**: Retrieve the list of favorited tracks by the user.

---

## 💻 API Authentication & Authorization

- **JWT Authentication**: Both admins and users are authenticated using JWT tokens. Admins have full permissions to manage content, while users have read-only access with the ability to favorite/unfavorite tracks.

- **Role-based Access Control (RBAC)**: Access to API endpoints is restricted based on user roles. Admin users have write access to all resources, while regular users have read-only access with the exception of favoriting tracks.

---

## 📝 Future Enhancements

1. **Playlist Sharing**: Allow users to share playlists with other users or on social media.
2. **Search Functionality**: Implement search functionality for albums, tracks, and artists.
3. **Personalized Recommendations**: Use algorithms to suggest albums and tracks based on user preferences.
4. **Advanced User Roles**: Implement more granular roles, such as curators or moderators, with specific permissions.

---

## 🚀 Running the Application

### 1. Clone the Repository
```bash
git clone https://github.com/yourrepo/music-app.git
cd music-app

