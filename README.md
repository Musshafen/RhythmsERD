# RhythmsERD

CREATE TABLE "Bands" (
"Id"                   SERIAL PRIMARY KEY,
"Name"                 TEXT NOT NULL,
"CountryOfOrigin"      TEXT,
"NumberOfMembers"      INT,
"Website"              TEXT,
"Style"                TEXT,
"IsSigned"             BOOLEAN,
"ContactName"          TEXT,
"ContactPhoneNumber"   TEXT
);


CREATE TABLE "Albums" (
"Id"           SERIAL PRIMARY KEY,
"Title"        TEXT,
"IsExplicit"   BOOLEAN,
"ReleaseDate"  TEXT
);


CREATE TABLE "Songs" (
"Id "          SERIAL PRIMARY KEY,
"TrackNumber"  TEXT,
"Title"        TEXT NOT NULL, 
"Duration"     TEXT
);


ALTER TABLE "Band" ADD COLUMN "AlbumId" INTEGER NULL REFERENCES "Albums" ("Id");

ALTER TABLE "Albums" ADD COLUMN "SongId" INTEGER NULL REFERENCES "Songs" ("Id");
