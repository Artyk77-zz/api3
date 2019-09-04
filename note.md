# Summary of Steps

1. Create Repo on Github
2. Clone it
3. Initialize with npm init -y
4. Add gitignore file, gitignore node
5. Make initial commit and set upstream with git push -u origin master (or your branch)
6. npm i express (will create node modules folder)
7. Make an api folder, set up index.js and server.js. Index.js should import server.js and do server.listen. Server.js contains all the server logic. Don't forget export module.exports = server;

        // index.js
        const server = require('./api/server.js');
        
        const port = 8000;
        server.listen(port, () => console.log(`Server listening on port ${port}`))

        // server.js
        const express = require('express');
        
        const server = express();
        
        server.get('/', (req, res) => {
            res.status(200).json({ api: 'up..'})
        })
        
        module.exports = server;

8. Add nodemon with npm i -D nodemon
9. Add this under scripts in package.json: "server": "nodemon index.js"
10. Now we can do npm run server, and test with Insomnia or Postman
11. Make another commit and push