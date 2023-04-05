# RhythmsERD

CREATE TABLE "Bands" (
"Id" SERIAL PRIMARY KEY,
"Name" TEXT NOT NULL,
"CountryOfOrigin" TEXT,
"NumberOfMembers" INT,
"Website" TEXT,
"Style" TEXT,
"IsSigned" BOOLEAN,
"ContactName" TEXT,
"ContactPhoneNumber" TEXT
);

CREATE TABLE "Albums" (
"Id" SERIAL PRIMARY KEY,
"Title" TEXT,
"IsExplicit" BOOLEAN,
"ReleaseDate" TEXT
);

CREATE TABLE "Songs" (
"Id " SERIAL PRIMARY KEY,
"TrackNumber" TEXT,
"Title" TEXT NOT NULL,
"Duration" TEXT
);

ALTER TABLE "Band" ADD COLUMN "AlbumId" INTEGER NULL REFERENCES "Albums" ("Id");

ALTER TABLE "Albums" ADD COLUMN "SongId" INTEGER NULL REFERENCES "Songs" ("Id");

INSERT INTO "Bands" ("Name", "CountryOfOrigin", "NumberOfMembers", "Website",
"Style", "IsSigned", "ContactName", "ContactPhoneNumber")
VALUES ('Counting Crows', 'US', '7', 'www.countingcrows.com', 'Alt Rock', 'TRUE', 'Adam Duritz', '555-555-1233');

SELECT \* FROM "Bands";

INSERT INTO "Albums" ("Title", "IsExplicit", "ReleaseDate")
VALUES ('August and Everything After', 'FALSE', '1993');

UPDATE "Bands" SET "AlbumId" = 1 WHERE "Id" IN (1);

INSERT INTO "Songs" ("TrackNumber", "Title", "Duration")
VALUES ('5', 'Anna Begins', '4:32');

UPDATE "Albums" SET "SongId" = 1 WHERE "Id" IN (1);

UPDATE "Bands" SET "IsSigned" = TRUE WHERE "Name" = "Counting Crows";

UPDATE "Bands" SET "IsSigned" = FALSE WHERE "Name" = "Counting Crows";

SELECT "Bands"."Name" FROM "Bands" JOIN "Albums" ON "Bands"."AlbumId" = "Albums"."Id";

SELECT "Albums"."Title" FROM "Albums" JOIN "Songs" ON "Albums"."SongId" = "Songs"."Id" ORDER BY "ReleaseDate";


SELECT * FROM "Bands" WHERE "IsSigned" = TRUE;