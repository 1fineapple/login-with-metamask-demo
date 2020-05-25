# Login with Portis

[![Build Status](https://travis-ci.org/amaurymartiny/login-with-metamask-demo.svg?branch=master)](https://travis-ci.org/amaurymartiny/login-with-metamask-demo)
[![David (backend)](<https://img.shields.io/david/amaurymartiny/login-with-metamask-demo.svg?label=deps%20(backend)&path=packages/backend>)](https://david-dm.org/amaurymartiny/login-with-metamask-demo?path=packages/backend)
[![David (frontend)](<https://img.shields.io/david/amaurymartiny/login-with-metamask-demo.svg?label=deps%20(frontend)&path=packages/frontend>)](https://david-dm.org/amaurymartiny/login-with-metamask-demo?path=packages/frontend)
[![](https://img.shields.io/badge/Buy%20me%20a%20tree-%F0%9F%8C%B3-lightgreen)](https://offset.earth/amaurymartiny)

Learn more as part of the corresponding blog article: ["One-Click Login with Blockchain: a MetaMask Tutorial"](https://www.toptal.com/ethereum/one-click-login-flows-a-metamask-tutorial).

Users must be authenticated to Learn and Earn. Once the extension button is clicked, we authenticate users by requiring them to sign up or sign in through Portis. Once integrated with an email and password, Portis manages a students private key inside their existing browser → Learn and Earn leverages Portis's end to end encryption architecture for security and participation. 

User clicks "Pair Wallet" The nonce field produces a random integer for each user in the back end (database). We call `web3.eth.coinbase` to get the current Portis users account’s public address. The user clicks login, and an API calls the backend —>  retrieves the nonce associated with the public address. The user receives request for confirmation and when he/she signs, the "signature" it is stored (nonce is changed) in the backend with the public address. 

React and web3 were the primary languages used for:

→ authentication 
→ stake of DAI
→ access to smart contract 

To stake the DAI,  the web3 library used:
"new web3.eth.Contract (JSONInterface [, address][, options])" 
adding objects to pass DAI and interact with the smart contract. 


#### Launching the demo using Docker:

Build and launch the backend:

```bash
cd backend
docker build -t login-backend .
docker run -d -p 8000:8000 login-backend
```

Build and launch the frontend:

```bash
cd frontend
docker build -t login-front .
docker run -d -p 3000:3000 login-frontend
```

You can then access the app on `localhost:3000`.

#### Start the demo using Yarn:

From the root folder of this repo, run

```bash
yarn install # Install the dependencies
yarn start # Will launch the frontend and the backend at the same time
```

The backend should be running on `localhost:8000`, and the frontend on `localhost:3000`.

Alternatively, you can start the frontend and the backend separately:

```bash
# Start the backend
cd packages/backend
yarn start

# Start the frontend
cd packages/frontend
yarn start
```


## Credits

If you liked this repo, you can go to amaurymartiny/login-with-metamask-demo to learn more about how it was created. 
---

