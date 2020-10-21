# Steps to reproduce

- Bootstrap RN project using TS template
`npx create-react-native-app my-app --template with-typescript`
- CD into the project
`cd my-app`
- Add project dependencies
`yarn add axios url //Not necessary if only using fetch`
 -Add client generator (as Dev dependency)
yarn add -D @openapitools/openapi-generator-cli`
- Create Api folder (for everything API related)
`mkdir Api`
- Download OAS file to Api folder
`curl https://petstore3.swagger.io/api/v3/openapi.json > ./Api/openapi.json`
- Add generator script to package.json
`npx add-project-script -n "openapi" -v "openapi-generator-cli generate -i ./Api/openapi.json -g typescript-fetch -o ./Api/generated"`
- Generate the client (requires JDK installed)
`yarn openapi`




# Scripts
```
"openapiaxios": "openapi-generator-cli generate -i ./Api/openapi.json -g typescript-axios -o ./Api/axios-generated",
"openapifetch": "openapi-generator-cli generate -i ./Api/openapi.json -g typescript-fetch -o ./Api/fetch-generated"
```
