# KIRI_NOTES.md - Heartbeat Monitoring

## Heartbeat Script
- Lokasi: `/projects/sandbox/heartbeat_simple.sh`
- Mode: sekali jalan (`--once`), lalu exit
- Jalur: `git push` ke branch `heartbeat`
- Pemanggilan: manual/event
- Tidak menggunakan loop, `nohup`, `setsid`, cron, atau systemd

## Testing
Jalankan satu heartbeat secara manual:

```bash
bash /projects/sandbox/heartbeat_simple.sh --once
```

Tanpa argumen juga melakukan tepat satu push:

```bash
bash /projects/sandbox/heartbeat_simple.sh
```

Verifikasi isi file di branch `heartbeat`:

```bash
git fetch origin heartbeat
git show FETCH_HEAD:heartbeat.json
```

## Status
- Tidak ada proses heartbeat detached.
- Tidak ada cron job.
- Tidak ada systemd service atau timer.
- Heartbeat dipanggil manual/event pada awal sesi, setelah task selesai, atau saat diminta dengan "cek heartbeat".

## Monitoring URL
- https://github.com/latifmuzakki289-commits/Superagent-deepseek/tree/heartbeat/heartbeat.json
