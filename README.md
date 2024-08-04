# Start React Native application with Expo

`npm start`

## Prepare to generate apk

`expo login`

`expo build:android`

`eas build:configure`

### Convert to apk in eas.json

```js
{
  "cli": {
    "version": ">= 10.2.2"
  },
  "build": {
    "preview": {
      "android": {
        "buildType": "apk"
      }
    },
    "preview2": {
      "android": {
        "gradleCommand": ":app:assembleRelease"
      }
    },
    "preview3": {
      "developmentClient": true
    },
    "production": {}
  },
  "submit": {
    "production": {}
  }
}
```

#### Generate the apk in expo

`npx cross-env EAS_NO_VCS=1 eas build -p android --profile preview`