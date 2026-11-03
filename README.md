Compose dan Caddyfile-nya sudah siap. Struktur foldernya:

Letakkan sertifikat (gabungan cert + chain) dan private key di folder certs/, lalu sesuaikan nama file di baris tls pada Caddyfile.
Folder certs di-mount read-only, jadi Caddy tidak akan mencoba mengubahnya. Karena memakai tls <cert> <key>, Caddy tidak meminta sertifikat Let’s Encrypt untuk domain itu.

Jalankan dengan docker compose up -d. Setelah mengganti sertifikat, reload tanpa downtime: docker exec caddy caddy reload --config /etc/caddy/Caddyfile.
