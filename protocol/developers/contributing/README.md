---
description: ¡Gracias por expresar tu interés en contribuir a PancakeSwap!
---

# Contribuir

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/developers-header.png)

PancakeSwap es un proyecto de código abierto. Si quieres contribuir al proyecto, esta sección está aquí para guiarte en tus primeros pasos con el equipo de PancakeSwap 🥞

Antes de comenzar cualquier desarrollo, te recomendamos que envíes un issue en Github para discutir el problema y la solución con el equipo.

## Configura tu entorno de desarrollo

Instala [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) si aún no lo has hecho.

1.  Haz un fork y clona el [repositorio](https://github.com/pancakeswap/pancake-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```
2.  Agrega el repositorio [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) como remoto. Por ejemplo:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
3.  Asegúrate de tener la última versión de la rama por defecto ( `develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
4.  Crea tu propia rama e instala las dependencias

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
5. ¡Feliz programación! 🎉

## Reglas de programación

Intentamos mantener la mayor consistencia posible entre cada uno de nuestros repositorios. Tu pull request tiene más posibilidades de ser aceptado si sigues las siguientes reglas y escribes código de alta calidad. **Comencemos** 💪

### Usa el UIKit

{% hint style="warning" %}
Revisa el [UI Kit](https://github.com/pancakeswap/pancake-frontend/tree/master/packages/uikit) antes de empezar a hacer cualquier cosa. Ya se han creado muchos componentes y no queremos que pierdas el tiempo reinventando la rueda 😉
{% endhint %}

Si es necesario crear una variante de un componente, usa el componente correspondiente en el UI Kit como base. Por ejemplo:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

### ¡Usa las herramientas!

La mayoría de nuestros repositorios usan [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started) y [Prettier](https://prettier.io). Asegúrate de estar familiarizado con las mejores prácticas de Typescript y habilita un plugin de ESLint y Prettier para tu IDE.

{% hint style="warning" %}
Asegúrate de que tu código esté formateado con Prettier y libre de cualquier error de ESLint antes de enviar un pull request.
{% endhint %}

### Algunas buenas prácticas

* Mantén los componentes tan pequeños y ["tontos"](https://en.wikipedia.org/wiki/Pure_function) como sea posible.
* Usa [Composición sobre Herencia](https://reactjs.org/docs/composition-vs-inheritance.html).
* Ten en cuenta que tu código será leído y mantenido por varios otros desarrolladores. Hazlo tan claro y fácil de actualizar como sea posible._​_

## Creando tu pull request

Tu código está listo para ser enviado a revisión, ¡felicitaciones! 🥳

* Todos los pull requests **deben** tener una descripción de lo que el PR intenta lograr.
* Mantén los pull requests **lo más pequeños posible**. Los pull requests más grandes deben dividirse en partes más pequeñas con una rama base dedicada. Por favor, etiqueta los PRs que se fusionan en tu rama base con la etiqueta `epic`.
* Si es posible, revisa tu propio PR y **agrega comentarios** donde se necesite aclaración adicional.

{% hint style="info" %}
Crea un [PR borrador](https://github.blog/2019-02-14-introducing-draft-pull-requests/) lo antes posible para que podamos ver tu progreso en curso.
{% endhint %}

### Título del Pull Request

El título de nuestros Pull Requests sigue [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) usando [commitlint](https://commitlint.js.org/#/).‌

_Más información en_ [_las directrices de Angular_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

| Tipo         | Descripción                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------- |
| **build**    | Cambios que afectan el sistema de compilación o dependencias externas (ejemplos de alcance: gulp, broccoli, npm)     |
| **ci**       | Cambios en nuestros archivos y scripts de configuración de CI (ejemplos de alcance: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Solo cambios en la documentación                                                                                     |
| **feat**     | Una nueva funcionalidad                                                                                              |
| **fix**      | Una corrección de errores                                                                                            |
| **perf**     | Un cambio de código que mejora el rendimiento                                                                        |
| **refactor** | Un cambio de código que no corrige un error ni agrega una funcionalidad                                              |
| **style**    | Cambios que no afectan el significado del código (espacios en blanco, formato, punto y coma faltantes, etc.)         |
| **test**     | Agregar pruebas faltantes o corregir pruebas existentes                                                              |

**Gracias por ayudarnos a hacer PancakeSwap aún más increíble** ❤
