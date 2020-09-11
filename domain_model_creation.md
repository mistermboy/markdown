# Módulo Domain Model Creation
## Resumen
Este módulo será el encargado de generar y desplegar de manera automática artefactos java (.jar) compilados sobre un repositorio de GitHub previamente configurado, de tal manera que estos puedan distribuirse.

ShEx-Lite es una aplicación que permite generar clases Java (POJOs) que representan un modelo de dominio. El sistema Hércules ASIO emplea ShEx-Lite para generar los modelos de dominio de la Arquitectura Semántica. Para tal fin se propone que los modelos de dominio correspondientes a cada versión de la ontología se puedan distribuir también compilados. De esta forma se pueden configurar instantáneas del proyecto. Una instantánea está compuesta por la ontología, sus shapes y el modelo de dominio correspondiente. La ontología se versiona por medio de GitHub. Sin embargo esto no se puede llevar al modelo de dominio compilado. Para versionar los artefactos se empleará un repositorio de GitHub haciendo uso del servicio GitHub Packages.

## Diagrama del módulo
![](./images/Diagrama%20arquitectura%20ASIO%20-%20Página%2010.png)

Previamente a la obtención de artefactos Java, la librería ShEx-Lite recibirá una serie de Shapes y se encargará de generar los POJOs escritos en código Java plano correspondientes. A continuación, un plugin para está librería sera las responsable de transformar dichos POJOs a artefactos de Java compilados para su distribución.
Una vez generados los artefactos,estos serán desplegados sobre un repositorio de GitHub donde serán publicados a modo de paquete utilizando el servicio GitHub Packages, permitiendo así el versioneado de los mismos.

Un paquete representa un software autocontenido y reutilizable que incluye código y metadatos. El servicio GitHub Packages es un servicio de alojamiento de paquetes, totalmente integrado con GitHub, que combina el código fuente junto con los paquetes en un mismo lugar, de manera que facilita la centralización del software.

## Datos de entrada
Los datos de entrada serán las Shapes y Prefijos que reciba la librería ShEx-Lite para su transformación a POJOs y posteriormente a artefactos Java a través de un plugin para la librería.
## Salidas esperadas
Los datos de salida del módulo, para este caso, se corresponden con una versión del artefacto de modelo de dominio subida a un repositorio de GitHub haciendo uso del servicio GitHub Packages con el versionado correcto.
## Posibles impedimentos
## Sistemas existentes similares
## Links
