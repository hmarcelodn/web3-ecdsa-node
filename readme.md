## ECDSA Node

This project is an example of using a client and server to facilitate transfers between different addresses. Since there is just a single server on the back-end handling transfers, this is clearly very centralized. We won't worry about distributed consensus for this project.

However, something that we would like to incoporate is Public Key Cryptography. By using Elliptic Curve Digital Signatures we can make it so the server only allows transfers that have been signed for by the person who owns the associated address.

### Video instructions
For an overview of this project as well as getting started instructions, check out the following video:

https://www.loom.com/share/0d3c74890b8e44a5918c4cacb3f646c4
 
### Client

The client folder contains a [react app](https://reactjs.org/) using [vite](https://vitejs.dev/). To get started, follow these steps:

1. Open up a terminal in the `/client` folder
2. Run `npm install` to install all the depedencies
3. Run `npm run dev` to start the application 
4. Now you should be able to visit the app at http://127.0.0.1:5173/

### Server

The server folder contains a node.js server using [express](https://expressjs.com/). To run the server, follow these steps:

1. Open a terminal within the `/server` folder 
2. Run `npm install` to install all the depedencies 
3. Run `node index` to start the server 

The application should connect to the default server port (3042) automatically! 

_Hint_ - Use [nodemon](https://www.npmjs.com/package/nodemon) instead of `node` to automatically restart the server on any changes.

### Approach
This project uses signatures to transfer between different addresses. The wallet will provide a random phrase which needs to be signed with the `./server/scripts/signature-tool.js` which will ask the phrase and the private key. The signature can be copied and pasted in the signature field and it will get the sender address and the balance. Then, you will be able to transfer to another account. In the `./server/outputs` you will get a few key-pairs I created for the sake of simplicity. If you want to generate key-pairs you can use `./server/scripts/generate.js`.

#### Signature tool 

```sh
node ./server/scripts/signature-tool.js
```

<img width="734" alt="Screen Shot 2023-04-02 at 20 17 36" src="https://user-images.githubusercontent.com/5897525/229384437-83bd9a35-3fb5-4317-b624-4825a26f58ba.png">

#### Sample Page
<img width="1396" alt="Screen Shot 2023-04-02 at 20 19 12" src="https://user-images.githubusercontent.com/5897525/229384400-7cdc1096-8522-4bb6-89ef-11fa786f0609.png">



