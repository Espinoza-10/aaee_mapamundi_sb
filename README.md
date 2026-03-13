# Maven – Resumen rápido

## ¿Qué es Maven?

**Apache Maven** es una herramienta de gestión y automatización de proyectos Java.

Permite compilar, probar, empaquetar y gestionar dependencias de forma automática.
Todo se configura mediante un archivo central llamado `pom.xml`.

---

## Conceptos básicos

### POM (Project Object Model)

Es el archivo `pom.xml`, donde se define:

* Información del proyecto (`groupId`, `artifactId`, `version`)
* Dependencias
* Plugins
* Configuración de compilación

Ejemplo básico:
```xml
<groupId>org.ejemplo</groupId>
<artifactId>mi-proyecto</artifactId>
<version>1.0.0</version>
```

---

## Ciclo de vida de Maven (Build Lifecycle)

El ciclo de vida principal está formado por fases que se ejecutan en orden:

| Fase     | Descripción                                 |
| -------- | ------------------------------------------- |
| validate | Comprueba que el proyecto es correcto       |
| compile  | Compila el código fuente                    |
| test     | Ejecuta los tests                           |
| package  | Empaqueta la aplicación (JAR/WAR)           |
| verify   | Verifica que el paquete es válido           |
| install  | Instala el paquete en el repositorio local  |
| deploy   | Publica el paquete en un repositorio remoto |

Ejemplo de ejecución:
```bash
mvn clean install
```

---

## Repositorios

Maven descarga las dependencias desde repositorios.

Tipos:

* **Local** → en el ordenador (`~/.m2`)
* **Central** → repositorio público de Maven
* **Remoto** → repositorios privados (Nexus, Artifactory)

---

## Dependencias

Las librerías necesarias para el proyecto se declaran en el `pom.xml`.

Ejemplo:
```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>8.0.33</version>
</dependency>
```

Maven descargará automáticamente la librería.

---

## Comandos Maven más usados

| Comando       | Función                                      |
| ------------- | -------------------------------------------- |
| `mvn compile` | Compila el proyecto                          |
| `mvn test`    | Ejecuta los tests                            |
| `mvn package` | Genera el JAR/WAR                            |
| `mvn install` | Instala el artefacto en el repositorio local |
| `mvn clean`   | Elimina la carpeta `target`                  |

---

## Estructura típica de un proyecto Maven
```
proyecto
│
├─ pom.xml
└─ src
   ├─ main
   │  ├─ java
   │  └─ resources
   └─ test
      └─ java
```

---

## Idea clave

Maven sigue el principio **"Convention over Configuration"**:
si respetas su estructura estándar de proyecto, **necesitas muy poca configuración**.

---
Fuentes: [ChatGPT](https://chat.openai.com) + [Claude](https://claude.ai)