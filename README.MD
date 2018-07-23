## Step by Step guide on vue.js + webpack to cordova packaging
@author @balaparthacloud
commands used and configuration to make cordova app.
1. create Android Package Kit  || .apk
2. create IOS Package ||  [ In progress ]

## arc

---

# Pre-requisites
>1. Download Node.js, update npm  : **npm install i -g npm**
>1. Install Cordova: **npm install -g cordova**
>1. Vue.js Basics : **npm install-g vue-cli**

---

# Create cordova app
```
cordova create carebnb
```

# Add android platform
```
cordova platform add android --save
```

# Build android project
```
cordova build android
```

# Run android project
```
cordova run android
```

# Remove generated content
```
cd carebnb
cd www
rm -rf * [ not able to remove use , sudo ]
```

# Copy carebnb vue project 
> download or locate : https://github.com/LeraLonde/CareBnB
> copy all content to www

# Build vue project, follow same step in carebnb documentation, ignore dev part
# Install dependencies
```
npm install
```
# Build for production with minification
```
npm run build
```

# Project changes before run android app
> Goto : config.xml in root of cordova build project 
> Edit : <name>Carebnb</name>
> Goto : carebnb/www/webpack.config.js
> Edit : __dirname looks below

```
module.exports = {
  entry: "./src/main.js",
  output: {
    path: path.resolve(__dirname, "../www/dist"),
```

# Cordova Generate apk file
```
cordova run android
/carebnb/platforms/android/app/build/outputs/apk/app-debug.apk
```

# Testing

> # Step 1
```
cordova emulate android
```

> # Step 2
```
expose your apk file via webserver to test
python -m SimpleHTTPServer 8000
download apk file into android mobile
install as untrusted source
```

---

# image builder for app
> http://appiconmaker.co/
