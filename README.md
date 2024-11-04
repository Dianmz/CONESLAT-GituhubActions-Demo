## CONESLAT 

### GitHubActions para Contribuciones Open Source

A continuación se muestra cómo crear un flujo de trabajo básico que se desencadena cuando se inserta código en el repositorio.

### Los pasos utilizados para correr el workflow son los soguientes:

1. Dentro del repositorio crear un directorio con el nombre: _.github/workflows/_ donde se almacanarán los archivos para el flujo.
2. Crear un archivo con el nombre: _learn-github-actions.yml_ y agregar el código a continuación:


```
name: learn-github-actions
run-name: ${{ github.actor }} is learning GitHub Actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'
      - run: npm install -g bats
      - run: bats -v

```

3. Confirmar los cambios y cargarlos al repositorio.
4. Visualizar el Flujo de Trabajo en la sección de _Actions_ de la página del repositorio.
5. En la barra lateral izquierda se debe visualizar el nombre del flujo de trabajo creado y al darcle click se puede observar el resumen de la ejecución de flujo de trabajo.

### Referencias

- [Plantillas-para-workflows](https://docs.github.com/es/actions/writing-workflows/using-workflow-templates)
- [Starter-workflows](https://github.com/actions/starter-workflows/tree/main)
