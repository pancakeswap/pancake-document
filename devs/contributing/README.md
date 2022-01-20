---
description: Gracias por mostrar tu interés en contribuir con PancakeSwap !
---

# Contribuciones

![](../../.gitbook/assets/dvs.png)

Pancake es un proyecto open-source. Si quieres contribuir con el proyecto, esta sección está aquí para guiarte a través de tus primeros pasos con el equipo de Pancake :pancakes:&#x20;

Antes de comenzar cualquier desarrollo, le recomendamos que envíe un problema en Github para discutir el mismo y su solución con el equipo. Si desea comunicarse directamente con el equipo de desarrollo, póngase en contacto con **@chef\_chungus** en Telegram ![](../../.gitbook/assets/Logo.svg)&#x20;

### Configurar tu entorno de desarrollo

1.  Haz un Fork del repositorio y [agrega un control remoto ascendente](https://docs.github.com/en/github/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork). Por ejemplo:

    ```bash
    $ git remote add upstream git@github.com:pancakeswap/pancake-frontend.git
    ```
2.  Asegúrese de que tiene la versión más reciente del Branch predeterminado ( `develop` or `master` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```
3.  Crea tu propio branch e instala las dependencias.

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```
4. Codea Feliz! :tada:&#x20;

### Reglas de Código

Tratamos de mantener la mayor coherencia posible entre cada uno de nuestros repositorios. Tu pull request tiene más posibilidades de ser aceptada si sigue algunas de las siguientes reglas y escribe código de alta calidad **Empecemos!** :muscle:&#x20;

#### Usa el UIKit

{% hint style="warning" %}
Mira el [UI Kit](https://github.com/pancakeswap/pancake-uikit) antes de empezar a hacer nada. Muchos componentes ya están creados, y no queremos que pierdas el tiempo reinventando la rueda :wink:&#x20;
{% endhint %}

Si es necesario crear una variante de un componente, utilice el componente correspondiente en el UI Kit como base. Por ejemplo:

```javascript
import styled from 'styled-components'
import { Button } from '@pancakeswap-libs/uikit'

const NewButtonVariant = styled(Button)`
  // custom styles here
`
```

#### Usa las Herramientas!

La mayorías de nuestras repos usan [Typescript](https://www.typescriptlang.org/docs), [ESLint](https://eslint.org/docs/user-guide/getting-started), y [Prettier](https://prettier.io). Asegúrese de que está familiarizado con las mejores prácticas de Typescript y habilite un complemento ESLint y Prettier para su IDE.

{% hint style="warning" %}
Asegúrese de que el código tiene el formato de Prettier y está libre de cualquier error de ESLint antes de enviar una pull request
{% endhint %}

#### Algunas Buenas Prácticas

* Mantenga los componentes lo más pequeños e ["idiotas"](https://en.wikipedia.org/wiki/Pure\_function) como sea posible.
* Use [Composición sobre Herencia](https://reactjs.org/docs/composition-vs-inheritance.html).
* Tenga en cuenta que el código será leído y revisado por varios otros desarrolladores. Haz que sea lo más claro y fácil de actualizar posible.

### Confirmación <a href="#committing" id="committing"></a>

Nuestros mensajes de confirmación siguen [Confirmaciones Convencionales  ](https://www.conventionalcommits.org/en/v1.0.0/)usando [commitlint](https://commitlint.js.org/#/).‌

| Tipo         | Descripción                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------- |
| **build**    | Cambios que afectan al sistema de compilación o a las dependencias externas (ámbitos de ejemplo: gulp, broccoli, npm)       |
| **ci**       | Cambios en nuestros archivos de configuración y scripts de CI (ámbitos de ejemplo: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Cambios sólo en la documentación                                                                                            |
| **feat**     | Una nueva característica/Función                                                                                            |
| **fix**      | Arreglo de un Bug                                                                                                           |
| **perf**     | Un cambio de código que mejora performance                                                                                  |
| **refactor** | Un cambio de código que no corrige un error ni agrega una característica                                                    |
| **style**    | Cambios que no afectan al significado del código (espacios en blanco, formato, falta de punto y coma, etc.)                 |
| **test**     | Agregar pruebas que faltan o corregir pruebas existentes                                                                    |

_Más en_ [_Angular's guidelines_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)_​_

### Creando tu pull request&#x20;

Su código está listo para ser enviado para su revisión, felicitaciones:partying\_face:&#x20;

* Una pull request **debe** tener una descripción dé qué es lo que la PR está tratando de lograr.
* Mantenga las pull request lo más pequeñas posible. Las pull request más grandes deben dividirse en fragmentos más pequeños con un branch base dedicado. Por favor, marque los PR que se están fusionando en su branch base con la etiqueta `epic`
* Si es posible, autor revea su PR y **agregue comentarios** donde sea necesaria una aclaración adicional.

{% hint style="info" %}
Crea un  [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) lo antes posible así nosotros podemos ver tu proceso en curso.
{% endhint %}

**Gracias por ayudarnos a hacer Pancake aún más impresionante** :heart:&#x20;
