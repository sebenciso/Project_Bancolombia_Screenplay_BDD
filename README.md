# Proyecto de pruebas automatizadas para Sufi- Bancolombia

Este proyecto contiene pruebas automatizadas utilizando Cucumber, Selenium y Serenity BDD. Con lenguaje JAVA

## Requisitos

- Java JDK 8 o superior
- Maven
- Tener instalado el IDE IntelliJ

## Instrucciones de ejecución

1. Clona el repositorio en tu máquina local.

2. Abre una terminal o línea de comandos y navega hasta el directorio del proyecto.

3. Ejecuta el siguiente comando para compilar y ejecutar las pruebas:

mvn clean verify


4. Después de que las pruebas se completen, se generará un informe en la carpeta `target/site/serenity`.

5. Abre el archivo `target/site/serenity/index.html` en tu navegador para ver el informe de Serenity.

## Ejecutar todos los feature del proyecto con chrome

```
mvn clean verify -Ddriver=Chrome
```
Ejecutar todos los feature del proyecto con Firefox

```
mvn clean verify -Dwebdriver.driver=firefox
```
Ejecutar todos los feature del proyecto con edge

```
mvn clean verify -Dwebdriver.driver="edge"

```
## Ejecutar el feature de Login

```
mvn clean verify -Dcucumber.options="src/test/resources/features/ValidarIngresarURL.feature"
```
## Ejecutar El Feature Para Los Simuladores De Créditos

```
mvn clean verify -Dcucumber.options="src/test/resources/features/ValidarIngresarSABERMAS.feature"

mvn clean verify -Dcucumber.options="src/test/resources/feature/SimuladorCreditoVehiculos.feature --tags @ValidacionSimuladorCreditoMotoAltoCilindraje"

mvn clean verify -Dcucumber.filter.tags="@ValidacionSimuladorCreditoMotoAltoCilindraje" -Dwebdriver.driver=chrome

mvn clean verify -Dtags="@ValidacionSimuladorCreditoMotoAltoCilindraje"

mvn clean verify -Dcucumber.options="--tags '@ValidacionSimuladorCreditoMotoAltoCilindraje'"


```

## Arquitectura (Arquetipo) del Proyecto

----- Módulo main
+ exceptions
  Clases que controlan las posibles excepciones técnicas y de negocios que se presentan durante la ejecución de pruebas
+ model
  Clases relacionadas con el modelo de dominio y sus respectivos builder cuando es necesario
+ tasks
  Clases que representan tareas que realiza el actor a nivel de proceso de negocio
+ interactions
  Clases que representan las interacciones directas con la interfaz de usuario
+ userinterface
  Page Objects y Page Elements. Mapean los objetos de la interfaz de usuario
+ questions
  Objetos usados para consultar acerca del estado de la aplicación
+ util
  Clases de utilidad
  ----- Módulo test
+ runners
  Clases que permiten correr los tests
+ step definitions
  Clases que mapean las líneas Gherkin a código java
+ features
  La representación de las historias en archivos cucumber# Project_Bancolombia_Screenplay_BDD
