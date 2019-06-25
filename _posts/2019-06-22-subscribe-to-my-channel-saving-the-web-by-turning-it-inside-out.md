---
title: 'Subscribe to my channel: saving the web by turning it inside out'
---

The Web is in crisis. Tim Berners-Lee himself is concerned about the "[downward plunge to a dysfunctional future](https://www.bbc.com/news/technology-47524474)." Facebook [leaks our personal data](https://en.wikipedia.org/wiki/Facebook%E2%80%93Cambridge_Analytica_data_scandal) and [gets hacked](https://techcrunch.com/2018/09/28/everything-you-need-to-know-about-facebooks-data-breach-affecting-50m-users/). Slack is slick, but expensive and designed around work.

The alternatives aren't much better. Email won't die, but it also will never be anywhere near as useful as we would hope it could be. SMS would be a great alternative, if it weren't so limited, [insecure](https://www.theverge.com/2017/9/18/16328172/sms-two-factor-authentication-hack-password-bitcoin), and spammable. 

Every app and website makes you sign an End User Licence Agreement you don't read stating just how much data you're giving them and how they have unlimited rights to use it, all so you can create an account on their system which they control. If you don't supply a Facebook or Google account, you have to supply a password, which they are certain to [mishandle](https://techcrunch.com/2019/04/18/instagram-password-leak-millions/) at some point.

The result is that your data is scattered around the Internet in different formats, which you may or may not be able to access. You might have a paper trail if your email has receipts, but you may have deleted them.

Does it have to be this way? Do we just give up and hope for the best? Do we continue to funnel our communication through companies that only seem to care when they get caught doing something less than ethical?

What if we turned all of this around? What if we made companies come to our websites, create accounts with us, and agree to our license agreements? What if we distributed our personal data on our own terms, and even had specific terms for specific types of data?

Sound wonderful, fantastical, and impractical? Let's see how it could work.

In today's world, the Web works like this: you have a browser, app, or some other client that goes to a remote server and makes a request. Anyone can make a request to the server, so the only way the server knows who made the request is to use a cookie. The cookie gets stored by the browser the first time the website is loaded, then gets sent back to the server whenever subsequent requests are made. 

Using cookies to identify users made sense for the time since web servers, overall computing power, and bandwidth were all much more expensive. However, the security implications of cookies have been [decried](https://cacm.acm.org/magazines/2001/5/7369-digital-village-caustic-cookies/abstract) for a long time now. Although modern browsers have implemented safeguards like [same-origin policy](https://en.wikipedia.org/wiki/Same-origin_policy) to reduce the security risks, the overall design of cookie-based sessions [hasn't changed much](https://en.wikipedia.org/wiki/HTTP_cookie#History).

This [client-server model](https://en.wikipedia.org/wiki/Client%E2%80%93server_model) has been the norm for over two decades now. But what if we added another piece into the model? The client would connect to this additional piece and use it to control everything. This could be known as a "channel." So the new model would be client-channel-server.

How then would adding this "channel" make anything better than what we currently have? The previous model assumed a [stateless](https://en.wikipedia.org/wiki/Stateless_protocol) connection between the client and the server. That is, the client connects to the server, the server sends back the requested information, then the connection ends. No new connection is made back to the server until the client initiates one. (Note: while there is now a way of having the [server push](https://developer.mozilla.org/en-US/docs/Web/API/Push_API) information back to the client, it's limited and still relies on [client-side coordination](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) to actually receive the messages.)

In contrast to the client, the channel would be always on and publicly addressable through [DNS](https://en.wikipedia.org/wiki/Domain_Name_System). The server would be able to go back to the channel at any time to deliver as much or as little information as necessary. It would behave in a way similar to email, but over HTTPS and authenticated.

But how would the server know to go to the channel in the first place? This would happen through an invitation. In client-channel-server, the client tells the channel to invite a server to connect. This invitation would be delivered over HTTPS with a token, the address of the channel, and the Terms of Service. The server would then decide whether to agree to the Terms of Service. If so, the server would connect back to the channel with the token. No passwords, no oAuth, and no accounts created through third-party platforms like Facebook.

The client can then keep a constant connection to the channel and receive any messages being sent to it. This could be through a browser, an app, or even through the operating system of the device. This constant connection eliminates the need for the device to connect to multiple servers just to receive messages.

The channel could also be used for sharing specific information. For instance, maybe you need to share your home address to have a package shipped to you. The server can request this through your channel and your channel can ask you if you want to share your address. 

But what if you are asked for your address with no shipment involved? The channel could tell you why the server is asking for your address and you can decide for yourself if you want to share it. The channel could also tell the server how long they can keep your address and how they can use it. For instance, you could authorize the server to retain your address for as long as your order is open, but no more.

If you decide you are done using a particular server, you can tell your channel to stop receiving messages from it. Then the channel could ignore the server going forward. The channel would also ignore any messages coming from servers that haven't been invited to the channel, eliminating a potential vector for spam.

Beyond servers, you could also connect your channel to someone else's channel. This would be accomplished by both of you sending invitations to each other's channels. From there, you could use the channels to send text and data, similar to the way SMS works.

So there it is: a way we could streamline web communication by having servers create accounts with our channels, rather than using clients to create accounts on servers. It won't be trivial to implement, but it's still possible with the reliable, affordable computing power available today.
