# Generate localhost SSL certificate for Angular CLI

This repository is a workaround for the "[WDS] Disconnected" refresh loop caused by a bug in one of the Angular CLI dependencies detailed here: https://github.com/angular/angular-cli/issues/4839#issuecomment-314608490

_Credit to the workaround goes to [veke](https://github.com/veke) as referenced in the link above_

## Instructions

1. Clone repository
2. `npm install`
3. `node gen`
4. Copy the SSL directory into your Angular project's root directory
5. Install the certificate to the Trusted Root store
6. Update package.json "start" script with `"start": "ng serve --ssl 1 --ssl-key ./ssl/server.key --ssl-cert ./ssl/server.crt"`

Now when you run `npm start`, you shouldn't see the "[WDS] Disconnected" error or the associated refresh loop