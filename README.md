[![KTOR](https://img.shields.io/maven-central/v/io.ktor/ktor)](https://mvnrepository.com/artifact/io.ktor)
[![Kotlin](https://img.shields.io/badge/kotlin-1.8.10-blue.svg?logo=kotlin)](http://kotlinlang.org)

# Erstellung einer einfachen Anwendung
Hier eine Schritt-für-Schritt-Anleitung zur Erstellung einer einfachen Anwendung mit Ktor:

## 1.
Um ein neues Projekt in Ihrer Entwicklungsumgebung zu erstellen, wählen Sie Ktor als Generator aus, geben Sie Ihrem Projekt einen Namen, wählen Sie einen Speicherort aus, geben Sie die Webadresse ein und nehmen Sie gegebenenfalls entsprechende Einstellungen vor:
![Screenshot_1](https://github.com/ktor-apps/sample-1-1-first/assets/132061267/4856448f-9271-4d74-8279-56c6a1d85141)

## 2.
Lassen Sie vorerst die Plugins unverändert und klicken Sie auf die Schaltfläche "Create":
![Screenshot_2](https://github.com/ktor-apps/sample-1-1-first/assets/132061267/8f26f913-4fb3-42c9-a67c-ac8d7643cd40)

## 3.
Nachdem IntellJ gestartet ist, sollten unter “..\src\main\kotlin\ch\ktorapps\” die Kotlin Datei “Application.kt” und unter “..\src\main\kotlin\ch\ktorapps\plugins” die “Routing.kt” vorhanden sein, mit folgenden Inhalt:

### Application.kt
```kotlin
package ch.ktorapps

import io.ktor.server.application.*
import io.ktor.server.engine.*
import io.ktor.server.netty.*
import ch.ktorapps.plugins.*

fun main() {
    embeddedServer(Netty, port = 8080, host = "0.0.0.0", module = Application::module)
    .start(wait = true)
}

fun Application.module() {
    configureRouting()
}
```

### Routing.kt
```kotlin
package ch.ktorapps.plugins

import io.ktor.server.routing.*
import io.ktor.server.response.*
import io.ktor.server.application.*

fun Application.configureRouting() {
    routing {
        get("/") {
        call.respondText("Hello World!")
        }
    }
}
```
## 4.
Eine Möglichkeit, um die Anwendung zu starten, besteht darin, den grünen Pfeil links neben der Main-Methode in der “Application.kt” zu verwenden:
![Screenshot_3](https://github.com/ktor-apps/sample-1-1-first/assets/132061267/2475fbd7-df34-40ef-b09d-8e1d853d6799)

## 5.
Dann sollte unter dem Fenster “Run”. (View\Tool Windows\Run oder Alt+4) in etwa folgende Meldung erscheinen:
![Screenshot_4](https://github.com/ktor-apps/sample-1-1-first/assets/132061267/6eb008ed-3d06-41fc-b30d-58fb10c0282e)

## 6.
Um die Anwendung zu testen, können Sie auf den Link "http://127.0.0.1:8080" klicken und Ihren Browser öffnen:
![Screenshot_5](https://github.com/ktor-apps/sample-1-1-first/assets/132061267/c5344fe6-8d38-4ec1-b173-ad096bc80a56)


## 7.
Das war's! Du hast erfolgreich eine einfache Anwendung mit Ktor erstellt. Dieses Beispiel kannst Du finden unter: https://github.com/ktor-apps/sample-1-1-first