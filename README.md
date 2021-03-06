# Gcorder

An Angular SPA that captures audio from the microphone and live uploads it directly to your google drive.

## Getting Started
- `npm install`
- [get your own developer clientId for google drive](https://developers.google.com/identity/sign-in/web/sign-in)
- create your environment as detailed in `src/environments/environment.sample.ts`
- `npm run serve`
- `http://localhost:4200`

## Usage
- you must sign in with a google account to use this app
  - you will only be asked to grant permission to create/read files created by this app
- once signed in, hit the big red button to start recording
  - then hit the pause button to pause
  - or the stop button to complete your recording
- then you can either play the file from browser memory using the built in player
  - or go to your google drive and see the file waiting for you!
    - (better UX for viewing your recordings coming soon)

## Sweet Snippets
- [custom rxjs operators](https://github.com/nigel-smk/gcorder/tree/develop/src/app/audio-recorder/operators)
- [live mp3 encoding with a web worker initialized by the rxjs `using` operator](https://github.com/nigel-smk/gcorder/blob/develop/src/app/audio-recorder/operators/mp3-encode.operator.ts)
  - [the web worker](https://github.com/nigel-smk/gcorder/blob/develop/src/worker/worker.js)
  - [angular cli configuration](https://github.com/nigel-smk/gcorder/blob/develop/.angular-cli.json#L10-L22)
- [integrating the Google gapi.auth2 library with Angular](https://github.com/nigel-smk/gcorder/blob/develop/src/app/google-oauth/google-auth.service.ts)
  - [using ngZone.run() to re-enter the Angular zone](https://github.com/nigel-smk/gcorder/blob/develop/src/app/google-oauth/google-auth.service.ts#L23)
- ["live" uploading files with Google Drive's resumeable upload](https://github.com/nigel-smk/gcorder/blob/develop/src/app/google-drive/resumeable-upload.service.ts)
- [storing a retrieving blobs from local storage](https://github.com/nigel-smk/gcorder/blob/develop/src/app/interface/recorder/recorder.component.ts#L73-L88)
- [nifty css transitions](https://github.com/nigel-smk/gcorder/blob/develop/src/app/interface/recorder/recorder.component.scss#L21)
- [an attempt to intercept 308 responses to mark them as successes](https://github.com/nigel-smk/gcorder/blob/develop/src/app/interface/resumable308-interceptor.service.ts)

Unsolicited code reviews welcomed!
