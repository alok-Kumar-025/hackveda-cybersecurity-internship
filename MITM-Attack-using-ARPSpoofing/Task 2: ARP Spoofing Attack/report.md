## Task 2: ARP Spoofing Attack

### Steps Performed

1. Enabled IP forwarding on Parrot OS:
   ```bash
   echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward
   ```

2. Hosted a local HTTP form using PHP:
   ```bash
   cd /tmp
   cat > index.php << 'EOF'
   <?php
    if ($_POST) {
    echo "Received: user=" . $_POST['user'] . " pass=" . $_POST['pass'];
    } else {
    echo '<form method="POST">User: <input name="user"><br>Pass: <input name="pass" type="password"><br><input type="submit"></form>';
    }
    ?>
    EOF
    sudo php -S 0.0.0.0:80
    ```

3. Victim (Windows 11) accessed the form via http://192.168.0.192 and submitted credentials.
- Confirmed successful interception through server logs and browser output.

> All activities performed in a closed, local lab environment. No external systems were targeted.
