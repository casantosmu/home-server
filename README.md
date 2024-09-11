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

3. **Run the playbook:**

   ```bash
   ansible-playbook playbook.yaml -i inventory.ini --ask-become-pass --ask-pass
   ```
