# LightningNFC
## Lightning Network related projects with a NFC tag (ring, card...) ##
A list of projects. Some of them are really basic and easy to reproduce.


## Receive payments with a NFC tag and a Lightning Wallet ###
A very simple project. 
<br>**You will be able to receive payments via Lightning Network using your NFC tag.**<br>
You will not need to open your app to receive the payments.

You need:
1. A low cost NFC tag, such as a ring or a card (search on Amazon or Aliexpress)
2. An Android device 
3. NFC Tools app (https://play.google.com/store/apps/details?id=com.wakdev.wdnfc&hl=it&gl=US)
4. A Lightning Wallet able to handle LNURL-pay and [Lightning Address](https://lightningaddress.com/), such as [Breez Wallet](https://breez.technology/) or [Zeus](https://zeusln.app/). You can also try with other wallets, I haven't yet.
5. A LNURL-pay link (you can create a new link with https://legend.lnbits.com/) or a Lightning Address

Many different Lightning wallets support 'lightning:' protocol handler and LNURL-pay, so you can create a simple string 'lightning:LNURL' and the app will open and set the payment screen. You will just need to enter the amount and confirm. 
<br>Some wallets are also able to read Lightning Addresses, so you can use the handler with a vanity wrapper: 'lightning:LNADDRESS'.

In this project we will basically add 'lightning:LNADDRESS' into the NFC tag, so we can receive payment by simply tapping the sender device with our NFC tag.

I created my Lightning Address using my [BTCpay Server](https://btcpay.davidcoen.it/) instance. The LN address I will use is ['donate@btcpay.davidcoen.it'](lightning:donate@btcpay.davidcoen.it).

Open NFC Tools app and go to Add a record.
You will need to add a custom URL / URI: enter your lightning URI and tap OK.
In my case I will add ['lightning:donate@btcpay.davidcoen.it'](lightning:donate@btcpay.davidcoen.it), without the quotation marks.

Then you just need to approach the NFC tag and the app will save the data into the NFC tag memory.

Once you tap on your device using your NFC tag, your default Lightning wallet will open. 
I decided to make Breez my default Lightning app for this test, so when I tap with my NFC tag, the app is lauched and it sets the payment.
I just need to enter the amount and send.

The result is this (click the image to see the video): 
<br>[![Watch the video](https://img.youtube.com/vi/I_NfYfOKgEY/sddefault.jpg)](https://youtu.be/I_NfYfOKgEY)

## Send payments with a NFC tag and a BTCpay Server POS ###
<br>**You can make "offline" payments thanks to LNURL-withdraw so you don't need a device with Internet connection.**


You need:
1. A low cost NFC tag, such as a ring or a card (search on Amazon or Aliexpress)
2. An Android device 
3. NFC Tools app (https://play.google.com/store/apps/details?id=com.wakdev.wdnfc&hl=it&gl=US)
4. A Lightning Wallet able to generate a LNURL-withdraw link or you can use LNbits (you can create a new demo link with https://legend.lnbits.com/).

Many different Lightning wallets support 'lightning:' protocol handler and LNURL-withdraw, but currently only BTCpay Server supports the LNURL-withdrawPOS (link to the repo will soon be public) flow, so you need to have a BTCpay Server instance, create a new virtual POS and enable LNURL NFC Support plugin by Andrew Camilleri.

In this project we will basically add 'lightning:LNURL-withdrawLink' into the NFC tag, so we can send payments by simply tapping the merchant's BTCpay Server POS device with our NFC tag.

I created my LNURL-withdraw link using [LNbits](https://legend.lnbits.com/) demo. 

Open NFC Tools app and go to Add a record.
You will need to add a custom URL / URI: enter your Lightning URI and tap OK.

Now in BTCpay Server, enter an amount into the POS, tap on "NFC & LNURL-withdraw" and tap the device with the NFC tag.

Once you tap on your device using your NFC tag, BTCpay will contact the server and will receive the funds.

The result is this (click the image to see the video): 
<br>[![Watch the video](https://img.youtube.com/vi/4m-FQoUAs50/sddefault.jpg)](https://youtu.be/4m-FQoUAs50)



