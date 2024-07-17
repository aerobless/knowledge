Running your own email server is time consuming and fairly difficult to do right. I personally use Gmail and am happy with it. However only the G-Suite Gmail supports adding custom domains for sending and receiving emails. So in order to make it work with free gmail we need email forwarding.

Some domain registars already offer email forwarding by default. Mine doesn't, so I'm using Cloudflare as a bridge.

1. Login to [Cloudflare](https://dash.cloudflare.com/) and add a website for your domain.
2. Change the nameserver configuration at the domain registrar to point to Cloudflare.
3. Go back to Cloudflare and select Email in the menu on the left side. Follow the wizard and setup email forwarding. Don't forget to add the necessary MX records.
4. Verify that the name servers were changed correctly and your domain points to Cloudflare.
5. Verify that you can receive forwarded emails.
6. Go into [Gmail settings -> accounts](https://mail.google.com/mail/u/0/#settings/accounts) add your custom address under the tab "Send mail as:". Follow the wizards to verify the address.
7. Verify that you can send emails from your custom domain via Gmail.
