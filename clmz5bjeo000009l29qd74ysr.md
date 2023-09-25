---
title: "The Request-Response Model"
datePublished: Mon Sep 25 2023 17:11:50 GMT+0000 (Coordinated Universal Time)
cuid: clmz5bjeo000009l29qd74ysr
slug: the-request-response-model
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/pf7BliMKKxM/upload/a313711f1565b06f2e4a4e8b776dfea3.jpeg
tags: backend, programming-ciovqvfcb008mb253jrczo9ye

---

Picture this scenario🖼️: You're in an interview, and the interviewer asks, "What backend framework do you know?" 🤔 Proudly, you respond that you know **Spring/Django/Express**. Following that, the interviewer asks, "Great! 🙌 Can you explain the request-response model used by the framework?" Assuming you don't know the answer, I've got this blog to help you understand the Request-Response model and what exactly happens when a client sends a request and the server sends a response.

If you know how it works, please stick around and read, because why not? 🤓

Firstly, let's explain what a client and a server are. A client is anything that sends a request! 📨 That's it. It could be a browser 🌐, your Postman app 📦, your terminal (cURL) 💻, or even your CLI application! 📟 The entity that initiates the request is called the Client. The server is what captures your request and responds to it, typically your Spring or Express app. 🌱🚀

Now, let's see the high-level steps involved in this entire process:

* 📨 Client sends a request to the server.
    
* 🕵️ Server parses the request.
    
* 🛠️ Server processes the request.
    
* 📬 Server sends a response.
    
* 📚 Client parses the response and consumes it!
    

It's that simple! 🤷‍♂️

We should note that in the server, parsing and processing are two different activities. Knowing that it is a GET request is part of parsing, and executing the respective action for the GET request is processing. 🤹‍♂️

The type of request body plays an important role in the parsing activity because parsing the request body incurs a cost. 📦 The different request body types are XML, JSON, and Protobufs. The parsing time is relatively higher for XML than JSON and Protobufs. Each has its pros and cons. JSON was adopted because it was easier to read and parse than XML. This process is called serialization and deserialization of data. 🧩

### **Applications 🌐**

* Most of the **web** works in this model only.
    
* **DNS** that translates domain names to IP addresses uses this model.
    
* Protocols like HTTP, and SSH work on this request-response protocol.
    
* **Remote procedure calls (RPC)** work on this model.
    
* **Database protocols** (Connecting with SQL and MongoDB databases) **📊🗄️**
    
* APIs that work on **REST, SOAP, and GraphQL 🚀📝** use this model.
    

### **Limitations 🙅‍♂️**

While the request-response model is widely used and versatile, it's important to acknowledge its limitations:

1. **Notification Service**: In scenarios where the client doesn't know when it will receive a notification from the server, such as in real-time messaging or push notifications, this model falls short. Clients would need to repeatedly poll the server for updates, which is inefficient and impractical for many use cases. WebSocket connections are often a more suitable alternative for real-time notifications.
    
2. **Chatting Applications**: Real-time chat applications face similar challenges. Clients can't rely solely on periodic requests to check for new messages, as it's not efficient or responsive. Instead, they often employ WebSocket or other event-driven solutions to instantly receive and display messages.
    
3. **Handling Lengthy Processes**: Activities that involve lengthy or unpredictable processing times, like uploading large files, are not well-suited for the request-response model. The client lacks awareness of when the task will be completed, and this can lead to timeouts, unresponsiveness, or failed requests. For such tasks, asynchronous processing or background jobs are preferable.
    

These disadvantages emphasize that while the request-response model is powerful and prevalent, it may not be the best fit for every situation, particularly when real-time or asynchronous interactions are required.

In conclusion, The Request-Response model is widely used and popular, and knowing the nitty-gritty of this model will give you a better understanding when you work with it. Next time, build a conversation with your office crush by explaining this model! Hope you get them :)