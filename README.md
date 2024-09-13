# Home Server Setup

**[Important notes](https://github.com/Luctia/ezarr?tab=readme-ov-file#important-notes)**

1. **Add your SSH public key:**
   Ensure your public key is available at `~/.ssh/id_ed25519.pub`.

2. **Create the inventory file:**
   Create `inventory.ini` with the following content:

   ```ini
   [home_server]
   SERVER_IP ansible_user=SSH_USER
   ```

   Replace `SERVER_IP` with your server's IP and `SSH_USER` with your SSH username.

3. **Create the secrets file:**

   The Cloudflare script updates your dynamic IP to ensure your domain always points to your server. Create `secrets.yaml` with your Cloudflare details:

   ```yaml
   zone_id: "YOUR_ZONE_ID"
   dns_record_id: "YOUR_DNS_RECORD_ID"
   api_token: "YOUR_API_TOKEN"
   domain: "yourdomain.com"
   ```

4. **Run the playbook:**

   ```bash
   ansible-playbook playbook.yaml -i inventory.ini --ask-become-pass --ask-pass
   ```
