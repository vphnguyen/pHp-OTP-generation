# pHp-OTP-generation
From Việt Nam with love.

DATABASE =========================================================

CREATE TABLE `verification` (
  `tenKH` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `ngay` timestamp NOT NULL DEFAULT current_timestamp(),
  `HASH` text COLLATE utf8_unicode_ci NOT NULL,
  `EMAIL` text COLLATE utf8_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;

PHP code =========================================================

$con=mysqli_connect(" a, b, b, d ");// server, user, password, database
1. Clean your expired rows.
2. Create new a row when meet a request from Client.
3. Save their ID and timestamp.
4. Get that timestamp.
5. Using your ID and timestamp as salt, hashed them MD5, SHA-1.
6. Get the numbers you need (4-6 digits) or hash them again.
7. Update the last row.

===========================
Dont forget to clean your table before you verifie any confirm from Client.

- V.P.Nguyễn -
