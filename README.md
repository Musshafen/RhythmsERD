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
"ContactPhoneNumber"   INT
);

