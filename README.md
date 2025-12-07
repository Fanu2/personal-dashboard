
# 🧹 MX Linux Storage, Cleanup & Performance Guide
**Personal System Maintenance Playbook**

This guide documents how to:
- Safely free disk space
- Prevent future disk overload
- Control AI model storage (Ollama / LM Studio)
- Optimize logs, cache, and system performance
- Keep MX Linux fast, clean, and stable long-term

---

## ✅ CURRENT SYSTEM STATUS (HEALTHY)

| Partition | Status |
|----------|--------|
| `/` Root | ✅ 58GB Free (47% Used) |
| Windows Recovery | ✅ Untouched & Safe |
| Cache & Logs | ✅ Optimized |
| AI Models | ✅ Cleared & Controlled |

Your system is now **stable, fast, and update-safe**.

---

# 🚀 QUICK CLEAN COMMAND (SAFE)

Run this anytime to instantly clean your system:

```bash
sudo apt clean && sudo apt autoclean && sudo apt autoremove --purge -y \
&& rm -rf ~/.cache/* && rm -rf ~/.local/share/Trash/* \
&& sudo journalctl --vacuum-size=100M
````

✅ Safe
✅ Frees GBs
✅ Prevents update failures

---

# 🔥 BIGGEST DISK HOGS (AI MODELS)

### 📍 Ollama Models

```
~/.ollama/models/blobs/
```

### 📍 LM Studio Models

```
~/.lmstudio/models/
```

✅ These files are **3–8GB each**
✅ 100% safe to delete
✅ Will auto-reinstall if needed again

### 🔥 Emergency AI Cleanup

```bash
rm -rf ~/.ollama/models/blobs/*
rm -rf ~/.lmstudio/models/*
```

---

# 🛡️ PREVENT FUTURE LOG BLOAT (IMPORTANT)

Limit system log size permanently:

```bash
sudo nano /etc/systemd/journald.conf
```

Add or edit:

```
SystemMaxUse=200M
```

Apply:

```bash
sudo systemctl restart systemd-journald
```

✅ Logs will **never exceed 200MB again**

---

# 🔍 FIND LARGE FILES ANYTIME

Find files larger than **1GB**:

```bash
find / -type f -size +1G -exec ls -lh {} \; 2>/dev/null
```

Check which folders in HOME are biggest:

```bash
du -h --max-depth=1 ~ | sort -h
```

---

# 🗂️ SAFE FOLDERS YOU CAN CLEAN ANYTIME

| Folder                 | Safe to Delete? | What It Is          |
| ---------------------- | --------------- | ------------------- |
| `~/.cache`             | ✅ Yes           | App & browser cache |
| `~/.local/share/Trash` | ✅ Yes           | Trash               |
| `~/.thumbnails`        | ✅ Yes           | Image previews      |
| `~/.ollama/models`     | ✅ Yes           | AI models           |
| `~/.lmstudio/models`   | ✅ Yes           | AI models           |

❌ Do NOT delete:

* `/usr`
* `/boot`
* `/lib`
* `/etc`

---

# 💾 RECOMMENDED DISK USAGE RULES

* ✅ Always keep **20 GB free on `/`**
* ✅ Never allow `/` above **85% usage**
* ✅ Large video files go to **external drive**
* ✅ AI models NEVER stay on `/` long-term

---

# 🤖 BEST PRACTICE FOR AI MODELS (PRO MOVE)

If you ever add a second drive, move AI models like this:

```bash
mv ~/.ollama/models /mnt/storage/ollama_models
ln -s /mnt/storage/ollama_models ~/.ollama/models
```

✅ No re-downloads
✅ No root disk filling
✅ Fully automatic

---

# 🧠 OPTIONAL PERFORMANCE BOOSTS

## ✅ Enable ZRAM (RAM Compression)

```bash
sudo apt install zram-tools
```

Perfect for:

* Low-RAM systems
* AI workloads
* Video editing
* Browsers with many tabs

---

## ✅ Reduce Swappiness (Less Disk Thrashing)

```bash
echo "vm.swappiness=10" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
```

---

# ⏱️ AUTOMATIC WEEKLY CLEANUP (SET & FORGET)

Create weekly cron job:

```bash
crontab -e
```

Add this line:

```
0 3 * * 0 sudo apt clean && sudo apt autoremove -y && rm -rf ~/.cache/*
```

✅ Auto-cleans every Sunday at 3 AM

---

# ✅ YOUR SYSTEM IS NOW OPTIMIZED FOR:

* 🎬 FFmpeg video processing
* 🤖 AI & local LLMs
* 🎧 Audio production
* 💻 Development work
* 🌐 Browsers & multitasking
* 🔒 Secure updates

---

# 🟢 FINAL GOLDEN RULE

> **If your system feels slow — always check disk usage first.**

```bash
df -h
```

Low disk space causes:

* App crashes
* Failed updates
* Freezes
* Boot errors

---

# ✅ YOU NOW OWN A CLEAN, FAST & FUTURE-PROOF MX LINUX SYSTEM 🚀
