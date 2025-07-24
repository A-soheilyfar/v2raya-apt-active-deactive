# فعال کردن service برای startup
`sudo systemctl enable v2raya`

# شروع service
`sudo systemctl start v2raya`

# چک کردن که درست کار می‌کنه
`sudo systemctl status v2raya`
برگردوندن repository:
```bash
bash# برگردوندن فایل repository
sudo mv /etc/apt/sources.list.d/v2raya.list.disabled /etc/apt/sources.list.d/v2raya.list 2>/dev/null || true
```

# چک کردن که برگشته
`ls /etc/apt/sources.list.d/ | grep v2ray`





روش 1: غیرفعال کردن repository v2raya
```bash
bash# پیدا کردن فایل repository v2raya
sudo find /etc/apt/sources.list.d/ -name "*v2raya*"
```

# یا بررسی همه فایل‌ها
```bash
ls -la /etc/apt/sources.list.d/
```

بعد فایل مربوط به v2raya را غیرفعال کنید:
```bash
bash# اگر فایل v2raya.list وجود دارد
sudo mv /etc/apt/sources.list.d/v2raya.list /etc/apt/sources.list.d/v2raya.list.backup
#یا اگر نام دیگری دارد، آن را تغییر نام دهید
```

حالا apt update کنید:
```bash
sudo apt update
```
بعد از اینکه کارتان تمام شد، فایل repository را برگردانید:
```bash
bash# برگرداندن فایل
sudo mv /etc/apt/sources.list.d/v2raya.list.backup /etc/apt/sources.list.d/v2raya.list
```
احتمالاً فایل v2raya در /etc/apt/sources.list.d/ است و کافی است آن را موقتاً rename کنید.
