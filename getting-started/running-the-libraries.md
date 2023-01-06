# Running the libraries

## Back-end
- Clone https://github.com/valtimo-platform/valtimo-docker-profiles and run the compose file for your desired edition
- Then run the gradle bootRun for your desired edition (for the gzac edition this is app/gzac/application/bootRun)

## Front-end
- Install all packages with npm install --legacy-peer-deps
- Then build all libraries with npm run libs-build-all
- And at last start the development server with npm start
- Remember that you need to run the back-end libraries as well to use Valtimo