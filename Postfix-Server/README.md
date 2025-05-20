📧 Postfix Email Server on Linux (CentOS 9)
This project demonstrates the configuration and troubleshooting of a Postfix mail server on a Linux system (RHEL-based), allowing the system to send emails externally via Gmail's SMTP relay.

🔧 What I Did
Verified if Postfix service has already been preinstalled
Installed and configured Postfix to send emails from a local Linux server.
Set up Gmail SMTP relay in /etc/postfix/main.cf.
Troubleshot DNS and hostname issues using tools like nslookup, dig, and tail -f /var/log/maillog.
🧠 What I Learned
The correct Gmail relay host is smtp.gmail.com, not smtp.mail.gmail.com (the latter results in DNS NXDOMAIN errors).
Duplicate 'smtp_tls_CAfile' create conflict that prevents mail server from sending email
Proper DNS resolution is crucial for outbound mail delivery.
Watching logs in real time with tail -f /var/log/maillog is essential for debugging Postfix issues.
🛠️ Commands Used
rpm -qa | grep postfix
dnf install postfix -y
dnf install s-nail
cd /etc/postfix
systemctl start postfix
systemctl enable postfix

# Send test email
sendmail kc.clara3@gmail.com

# Check logs
tail -f /var/log/maillog

# DNS checks
nslookup smtp.gmail.com
