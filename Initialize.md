# SDK & Gradle Errors
- Home
  - Android Studio Proxy ➙ `HTTP:fodev.org:8118` 
- ISC
  - Run Clash for Windows 
  - Run ProxyCap
    - Add Proxy ➙ `HTTPS:127.0.0.1:7890`
    - Add Rule ➙ `Port:8118`
  - Android Studio Proxy ➙ `HTTP:fodev.org:8118`
- Tip
  - SSHTunnel for SDK ➙ `ssh -D 1080 -f -C -q -N root@89.106.206.235`
  - Android Studio Proxy ➙ `SOCKS:127.0.0.1:1080`

# Enable SafeArgs
- build.gradle (Project:WiFi)
  ```kotlin
  plugins {
    id("com.android.application") version "8.2.0" apply false
    id("org.jetbrains.kotlin.android") version "1.9.10" apply false
    id("androidx.navigation.safeargs.kotlin") version "2.7.6" apply false
  }
  ```
- build.gradle (Module:app)
  ```kotlin
  buildscript {
    repositories {
        google()
        mavenCentral()
    }
    dependencies {
        val navVersion = "2.7.6"
        classpath("androidx.navigation:navigation-safe-args-gradle-plugin:$navVersion")
    }
  }

  plugins {
      id("com.android.application")
      id("org.jetbrains.kotlin.android")
      id("androidx.navigation.safeargs.kotlin")
  }
  ```
   
# Telegram Bot
- Create API Token by BotFather which has blue sign.
```bash
/newbot
# define botname and username
```

- Get Chat ID (392224413)
```bash
https://api.telegram.org/bot6589081160:xxxxxxxxxxxx/getUpdates
```

- Use Chat ID to send message to yourself
```bash
https://api.telegram.org/bot6589081160:xxxxxxxxxxxxxxxx/sendMessage?chat_id=392224413&text=Hello%20from%20your%20bot
```
