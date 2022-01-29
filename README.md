# LightningNFCRing
## Lightning related projects with a NFC ring ##
A list of projects. Some of them are really basic and easy to reproduce.

### Receive payments with a NFC ring and a Lightning Wallet ###
A very simple project. you will be able to receive payments via Lightning Network using your NFC ring.
You will not need to open your app to receive the payments.

You need:
1. A low cost NFC ring (search on Amazon or Aliexpress)
2. An Android device 
3. NFC Tools app (https://play.google.com/store/apps/details?id=com.wakdev.wdnfc&hl=it&gl=US)
4. A Lightning Wallet able to handle LNURL-pay and [Lightning Address](https://lightningaddress.com/), such as [Breez Wallet](https://breez.technology/) or [Zeus](https://zeusln.app/). You can also try with other wallets, I haven't yet.
5. A LNURL-pay link (you can create a new link with https://legend.lnbits.com/) or a Lightning Address

Many different Lightning wallets support 'lightning:' protocol handler and LNURL-pay, so you can create a simple string 'lightning:LNURL' and the app will open and set the payment screen. You will just need to enter the amount and confirm. 
<br>Some wallets are also able to read Lightning Addresses, so you can use the handler with a vanity wrapper: 'lightning:LNADDRESS'.

In this project we will basically add 'lightning:LNADDRESS' into the NFC tag of our ring, so we can receive payment by simply tapping the sender device with our NFC ring.

I created my Lightning Address using my [BTCpay Server](https://btcpay.davidcoen.it/) instance. The LN address I will use is ['donate@btcpay.davidcoen.it'](lightning:donate@btcpay.davidcoen.it).

Open NFC Tools app and go to Add a record.
You will need to ad a custom URL / URI: enter your lightning URI and tap OK.
In my case I will add ['lightning:donate@btcpay.davidcoen.it'](lightning:donate@btcpay.davidcoen.it), without the quotation marks.

Then you just need to approach the NFC ring and the app will save the data into the NFC tag memory.

Once you tap on your device using your NFC ring, your default Lightning wallet will open. 
I decided to make Breez my default Lightning app for this test, so when I tap with my NFC ring, the app is lauched and it sets the payment.
I just need to enter the amount and send.

The result is this (click the image to see the video): 
[![Watch the video](https://img.youtube.com/vi/I_NfYfOKgEY/sddefault.jpg)](https://youtu.be/I_NfYfOKgEY)

