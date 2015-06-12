# TODO

## expected version : 2.0.0

1. rewrite ini utilities, dan di-bash-function-kan. sementara ini khazanah per-coding-an bash gw masih ecek2, murni pake "FUNGSI IF" (dibaca pake logat Firman@PDAM Makassar). Semoga aja ke depan bisa lebih "magic" ini apps.
2. menambahkan fitur black-magic yg lebih "magical" : 
   1. wizard untuk create/grant user berdasarkan db.conf
   2. clone template data BPS, localization, Bank-bank di indonesia yang ter-disintegrasi dengan paket data model kita (codingaja_kernel)
   3. membuat generator sandbox `codingaja_kernel.sql` berikut default2 function kita (pengen gw sih, dibuat kayak `composer.json` —> ambil repo-repo template tabel yg ada.)
   4. wrapping `mysqltuner.pl` untuk analisis & benchmarking database
   5. monitoring slow query
3. membuat `local.db.conf` supaya bisa di-apply per-developer.
