# Cheat Sheet: Deploying Node Apps on Heroku


### Initialize and Deploy

1. In terminal, type `brew install heroku/brew/heroku`

2. Run `npm init` if you haven't already

3. `npm i dotenv`

4. `require('dotenv').config()` at the beginning of your Node js code (server.js)

5. `node -v` and add the version number to package.json 

   ```json
     "engines": {
       "node": "15.0.x"
     }
   ```

6.  `heroku login`

7. `heroku create`

8. `git init`

9. Save `web: npm start` or `web: node server.js`  to a file named `Procfile` with no extension and upload it to your root

10. If you don't already have a .gitignore file, create one in the root of your project and add files/folders such as `node_modules/`

11. `git add .`

12. `git commit -m "Add your comments here"`

13. `git show-ref` to see if your branch is named `main` or `master

14. `git push heroku main` or `git push heroku master`

14.5  If you enounter an error, run `heroku create` again

15. `heroku ps:scale web=1`

16. `heroku open`

17. `heroku logs --tail` to check logs if there's a problem

18. `heroku local web`



### Deploy to Heroku

1. `git add .`
2. `git commit -m "Add your comments here"`
3. `git push heroku main`
4. `heroku local web` or `heroku open`



### Environmental/Config Variables

1. `npm i dotenv`
2. `require('dotenv').config()` at the beginning of your Node js code (server.js)
3. `KEY=value` in .env file
4. `const key = process.env.KEY` in your Node js code
5. If your Node project contains a web server, you need to specify that it uses the right port number.  Heroku will set an environmental var named `PORT` that you can use, as in `port = process.env.PORT || 3000`
