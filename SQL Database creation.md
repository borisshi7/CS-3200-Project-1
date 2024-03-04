# SQL Database creation

```sql
CREATE TABLE "Artists" (
	"artist_id"	INTEGER,
	"name"	TEXT,
	"contactEmail"	TEXT,
	"phoneNumber"	TEXT,
	PRIMARY KEY("artist_id")
);

CREATE TABLE "ArtistsAccount" (
	"account_id"	INTEGER,
	"artist_id"	INTEGER,
	"socialMediaAccountId"	TEXT,
	"photoStockWebsiteId"	INTEGER,
	FOREIGN KEY("artist_id") REFERENCES "Artists"("artist_id"),
	PRIMARY KEY("account_id")
);

CREATE TABLE "Authentication" (
	"artist_id"	INTEGER,
	"authenticationUrl"	TEXT,
	"authenticationToken"	TEXT,
	"authenticationStatus"	TEXT,
	PRIMARY KEY("artist_id")
);

CREATE TABLE "Camera" (
	"camera_ID"	INTEGER,
	"photo_ID"	INTEGER,
	"cameraName"	TEXT,
	"lens"	TEXT,
	FOREIGN KEY("photo_ID") REFERENCES "Photos"("photo_id"),
	PRIMARY KEY("camera_ID")
);

CREATE TABLE "PhotoTags" (
	"tag_id"	INTEGER,
	"photo_id"	INTEGER,
	"tag"	TEXT,
	PRIMARY KEY("tag_id")
);

CREATE TABLE "Photos" (
	"photo_id"	INTEGER,
	"artist_id"	INTEGER,
	"title"	TEXT,
	"description"	TEXT,
	"dateAndTimeTaken"	TEXT,
	"gps_longitude"	REAL,
	"gps_latitude"	REAL,
	"height"	INTEGER,
	"width"	INTEGER,
	"size_mb"	REAL,
	FOREIGN KEY("artist_id") REFERENCES "Artists"("artist_id"),
	PRIMARY KEY("photo_id")
);

CREATE TABLE "TimePost" (
	"photo_id"	INTEGER,
	"timeForPosting"	TEXT,
	PRIMARY KEY("photo_id")
);
```

