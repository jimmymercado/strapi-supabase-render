# 🚀 Getting started with Strapi
Strapi comes with a full featured [Command Line Interface](https://docs.strapi.io/dev-docs/cli) (CLI) which lets you scaffold and manage your project in seconds.

### ⚙️ install strapi 

You can [Learn more](https://docs.strapi.io/dev-docs/quick-start) from Strapi's Quickstart Docs

```
npx create-strapi-app@latest my-strapi-project --quickstart
or
yarn create strapi-app my-strapi-project --quickstart
```

##### ⚠️ In Windows, if you encounter a `MODULE_NOT_FOUND` Error:
Remove `node_modules` and `package-lock.json`, then reinstall all dependencies
```
rm -rf node_modules
rm package-lock.json
npm install
```

### 🚦 `starting strapi`
1. after completing the installation, run `npm run start` 
2. to check if strapi runs locally, in your browser, go to http://localhost:1337/admin/auth/register-admin
3. If successful, stop the server then install [node postgres](https://www.npmjs.com/package/pg), then start the app again to check if everything is running locally
   ```
   npm install pg
   npm run start
   ```



# 🚀 Getting started with Supabase
Supabase is an open source Firebase alternative, creating projects for a Postgres database, Authentication, instant APIs, Edge Functions, Realtime subscriptions, Storage, and Vector embeddings.

### ✏️ login/signup for a supabase account
1. go to https://supabase.com/dashboard to login or create a new account
2. create a new Project
3. go to the Project Settings ⇒ Configurations ⇒ Database
4. go to the Connection Parameters section to copy each item to the postgres section of `\config\database.js` file
   ```
    const connections = {
      ...
    postgres: {
      connection: {
        connectionString: env('DATABASE_URL'),
        host: env('DATABASE_HOST', 'localhost'),
        port: env.int('DATABASE_PORT', 3306),
        database: env('DATABASE_NAME', 'strapi'),
        user: env('DATABASE_USERNAME', 'strapi'),
        password: env('DATABASE_PASSWORD', 'strapi'),
        ssl: env.bool('DATABASE_SSL', false) && {

   ```
5. OR a better way is to put all env vars in the `.env` file like so:
   ```
    #supabase postgres
    DATABASE_HOST=value-from-Connection-Params-in-Supabase
    DATABASE_PORT=value-from-Connection-Params-in-Supabase
    DATABASE_NAME=postgres
    DATABASE_USERNAME=value-from-Connection-Params-in-Supabase
    DATABASE_PASSWORD=value-from-Connection-Params-in-Supabase

   ```
6. save

# 📦  Push to Github 
1. go to github.com, login then create a new repository
2. after creating a new repo, go back to the codebase and run
   ```
   git remote add origin git@github.com:your-user-name/your-git-repo-name.git
   git branch -M main
   git push -u origin main
   ```

# 🚀 Getting started with Render
Render is a cloud hosting provider that can run every shape and size of application: static websites, dynamic web apps, scheduled cron jobs—you name it. It natively supports many popular programming languages, like Node.js, Python, and Ruby.

### ✏️ login/signup for a supabase account
1. go to https://render.com/ to login or create a new account
2. at the Dashboard, create a new Web Service
3. link your Github repo
4. add `Environment Variables` using the values you have from the the `.env` file
5. click Deploy Web Service and wait to complete
6. after successful deploy, you should be able to go to your Strapi site https://your-render-service-NAME.onrender.com/admin
  


<!-- ## ⚙️ Deployment



## 📚 Learn more



## ✨ Community -->

