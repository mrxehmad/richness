you can use the regex pattern `(?i)vpn` to block domains containing "vpn" in a **case-insensitive** manner. Here’s how to add it to Pi-hole:

### 1. **Via Pi-hole Admin Interface:**
1. Open the Pi-hole admin panel:  
   - `http://pi.hole/admin` or `http://<Your-Pi-hole-IP>/admin`
2. Go to **"Group Management" > "Domain Lists" > "Blacklist"**.
3. Click on the **"Regular Expression"** tab.
4. Add the following regex rule:

   ```
   (?i)vpn
   ```

5. Click **"Add"**, then restart Pi-hole's DNS service:

   ```bash
   pihole restartdns
   ```

---

### 2. **Via Command Line (SSH):**
If you prefer using the command line, SSH into your Pi-hole device and run:

```bash
pihole --regex '(?i)vpn'
```

This will add the regex to block any domain containing "vpn" (case-insensitive).

---

### 3. **Verification:**
You can check if a domain is blocked by running:

```bash
pihole -q vpnexample.com
```

If blocked, it will show up in the query logs.