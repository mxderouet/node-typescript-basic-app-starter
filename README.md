# Basic Typescript Node starter project

Just follow this tutorial: 
https://www.learnwithjason.dev/blog/modern-node-server-typescript-2024


## Set up the project:
```
mkdir my-node-app
cd my-node-app/
git init
npm init -y
npm i -D typescript ts-node @types/node
npx tsc --init
```

## Next, open package.json and add the following:
```
{
  "engines": {
    "node": ">=20.6.0"
  },
  "name": "my-node-app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "tsc",
    "dev": "node --env-file=.env --watch -r ts-node/register src/index.ts",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Jason Lengstorf <jason@learnwithjason.dev>",
  "license": "ISC",
  "devDependencies": {
    "@types/node": "^20.11.17",
    "ts-node": "^10.9.2",
    "typescript": "^5.3.3"
  }
}
```

## Add environment variables, if needed create .env and put any secrets inside:
```
TEST_VALUE=hello
```

## Create the main Node app file, create src/index.ts and put something inside:
```
function test(): void {
  console.log(process.env.TEST_VALUE);
}

test();
```

## Start the Node server and test live reload
```
npm run dev
```