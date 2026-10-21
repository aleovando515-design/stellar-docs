  ##) Las relaciones públicas deben ser revisadas y aprobadas antes de fusionarse. Busque una aprobación o una pregunta de seguimiento.        Documentación estelar y referencia API 🌌           Documentación estelar y referencia API 🌌                 Documentación estelar y referencia API 🌌        <!--      Documentación estelar y referencia API 🌌           Documentación estelar y referencia API 🌌         <!-- omitir en toc -->           Documentación estelar y referencia API 🌌           <!-- omitir en toc -->           Documentación estelar y referencia API 🌌           <!-- omitir en toc -->          Documentación estelar y referencia API 🌌          <!-- omitir en toc -->          Documentación estelar y referencia API 🌌        <!--      Documentación estelar y referencia API 🌌           Documentación estelar y referencia API 🌌        <!-- omitir en toc -->           Documentación estelar y referencia API 🌌           <!-- omitir en toc -->           Documentación estelar y referencia API 🌌           <!-- omitir en toc -->           Documentación estelar y referencia API 🌌           <!-- omitir en toc -->          Documentación estelar y referencia API 🌌          <!-- omitir en toc -->          Documentación estelar y referencia API 🌌        <!--      Documentación estelar y referencia API 🌌           Documentación estelar y referencia API 🌌        

-[Estelar]Estelar]

##      Tabla de contenidos      <!-- omitir en toc -->
4815163344708337
- [Contribuyendo](#contribuyendo)
- [Inicio rápido.](
  - [Requisitos previos](#prerrequisitos)
  - [desarrollo](#desarrollo)
- [Estructura del repositorio.](#repositorio-estructura)
- [Usando Markdown.](#using-markdown)
  - [Básicos de Markdown](#markdown-básicas)
  - [Marcado personalizado](#clatura)
    - [Alerta](#alerta)
    - [Ejemplo de código.](#ejemplo de código)

##      Contribuyendo    

¡Las contribuciones son más que bienvenidas! ¡Gracias! 🎉

     Para
detalles sobre cómo contribuir a los diversos repositorios de Stellar. Por favor, tome especial
    Nota del      [Código de conducta.][CoC].

   Nuestro sitio de documentación se construye utilizando     [Docusaurus][Docusaurus]. El contenido es
   escrito en     [MDX][mdx], que añade un montón de posibilidades interesantes. Incluso si estás
No está familiarizado con el marcado simple, ¡no temas! Todavía puedes contribuir en un
útil y significativa. Markdown es súper fácil de aprender, y vendrá bastante.
Naturalmente, después de solo un poco de práctica. Siempre puedes ayudar a corregir errores tipográficos, ortografía,
Y enlaces rotos, también.

Puede contribuir a los documentos de varias maneras:

-   ¿Ves algo que necesita ser corregido en los documentos, como un error en el código o un error tipográfico? Archivo a   [solicitud de extracción (PR)](https://github.com/stellar/stellar-docs/pulls)  proponer corregir el error;
-  ¿Crees que falta contenido útil en los documentos, como una guía específica de instrucciones o una pieza de contenido explicativo? Archivo y  [cuestión](https://github.com/stellar/stellar-docs/issues)  explicar lo que le gustaría ver (asegúrese de buscar los problemas existentes para evitar la duplicación);
   Documentación estelar y referencia API 🌌   <!-- omitir en toc -->Bienvenido al repositorio oficial de...     Contribuyendo ](https://github.com/stellar/stellar-docs/issues) explaining what you’d like to see (these will be added to the Ideas section on the [Dev Docs board](https://github.com/orgs/stellar/projects/56/views/1) for discussion);
  Hacer  

#alerta

#alerta
) Issues will be prioritized, labeled, and assigned (if possible). You can check the status of your issue on the Dev Docs board. The status of issues according to the column is:
  <!-- omitir en toc --> Bienvenido al repositorio oficial de...   
  - Backlog: these issues are not prioritized or actively being worked on.
  - To Do: these issues are prioritized and will be worked on soon.
  - In Progress: these issues are currently being worked on.
  - Blocked: these issues are being worked on but are blocked for some reason and need attention.
  - Done: these issues have been completed and can be closed.

If you have questions, feel free to ask in the [Stellar Developer Discord](https://discord.gg/stellardev).

## Quick Start
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)][codespaces]
[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)][gitpod]

### Prerequisites

To begin development on the documentation, you will first need to install the following:

- Node.js (v22, or higher): see https://nodejs.org/en/download/package-manager for details for your system
- npm: e.g. `sudo apt install npm` on Ubuntu
- yarn: `npm install yarn`
  - If you're getting dependency errors, try using `npm install yarn --legacy-peer-deps`
  - After `install` command succeeds run `corepack enable && corepack prepare yarn@stable --activate` to actually get yarn

### Development

Once all the prerequisites have been installed, you can run the following commands:

```bash
git clone https://github.com/stellar/stellar-docs
cd stellar-docs
yarn install
npx docusaurus start
```

This will begin the development server, and open a browser window/tab pointing
to `http://localhost:3000/docs/`. This development server will auto-reload when
it detects changes to the repository.

After you've made your changes, use the following commands to ensure the consistent
MDX file formatting and style across the repository:

```bash
npm run check:mdx # this will search for problems in the MDX files
npm run format:mdx # this will fix any problems that were found
```

## Repository Structure

- `/docs/` Contains all the documentation content. If you're contributing to the
  actual documentation, rather than site functionality, this is likely where you
  will want to be.
  - `/docs/<subdirectory>/` Each subdirectory inside the `docs` directory
    contains content documents relating to a common idea (asset issuance, or
    running a validator node, for example). There can also be subdirectories
    nested even further, which will follow the same rules. The location of a
    document within this directory structure will have a direct impact on the
    URL given to the document on the site (unless there is metadata or front
    matter that overrides these defaults.)
  - `/docs/<subdirectory>/_category_.json` This file contains information that
    determines the directory's location and position within the site's sidebar.
  - `/docs/<subdirectory>/<filename>.mdx` The actual documents live in these
    files (written in Markdown), and also contains "front matter" which can
    specify configuration parameter for the document's display, URL, etc. **All
    filenames must use dashes for spaces instead of spaces or underscores**
- `/src/` Contains non-documentation files like custom React components and
  styling.
- `/static/` Contains static assets. Anything in this directory will be copied
  to the root of the final `build` directory.
- `/nginx/` Contains configuration used to deploy and host the docs site. Unless
  you're part of Stellar's IT Ops team, you probably don't need to do anything
  with this. *Exception*:
  - `/nginx/includes/redirects.conf` Contains redirect rules to avoid broken
    links. If you find a broken link somewhere out in the wilds of the internet,
    and there's no way for it to be changed, a redirect could be a useful tool.
    (Note our aim isn't to *completely* avoid 404 pages for a user. That would
    be impossible and impractical. These redirects are evaluated on a
    case-by-case basis, and it may be determined that a redirect isn't the right
    approach in some instances.)

## Using Markdown

### Markdown Basics

If you're unfamiliar with Markdown, there are **loads** of good tutorials and
cheat sheets out there. Check out some of these resources to get a handle on the
basics:

- [CommonMark cheat sheet and tutorial][commonmark]
- [Interactive markdown tutorial][tutorial]
- [The markdown guide][guide]

### Custom Markdown

Our repository uses some custom React components that can be used inside the
`MDX` documents. Use them as follows:

**Make sure that there is an empty line within the wrapper.** For example,

```text
<Alert>
<!-- EMPTY LINE AFTER THE COMPONENT'S OPENING TAG IS REQUIRED -->

Note: the testnet is reset every three months, so when building on it, make sure you have a plan to recreate necessary accounts and other data. For more info, check out the [best practices for using the testnet](../../learn/fundamentals/networks.mdx).

<!-- EMPTY LINE BEFORE THE COMPONENT'S CLOSING TAG IS REQUIRED -->
</Alert>
```

#### Alert

![Testnet reset alert](./readme-imgs/alert.png)

`<Alert />` is used to convey hints, warnings, etc. For example,
[Build a SEP-31 Anchor on Testnet][alert-example]

```markdown
import { Alert } from "@site/src/components/Alert";

<Alert>

Note: the testnet is reset every three months, so when building on it, make sure you have a plan to recreate necessary accounts and other data. For more info, check out the [best practices for using the testnet](../../fundamentals-and-concepts/testnet-and-pubnet).

</Alert>
```

#### Code Example

![Create account code example](./readme-imgs/code-example.png)

`<CodeExample />` is a code snippet component. You can include snippets for more
than one language. See an example including a snippet for `JavaScript` and
`Python` below. It is using [Prism React Renderer][prism] for syntax
highlighting.

````markdown
import { CodeExample } from "@site/src/components/CodeExample";

<CodeExample>

```js
// create a completely new and unique pair of keys
// see more about KeyPair objects: https://stellar.github.io/js-stellar-sdk/Keypair.html
const pair = StellarSdk.Keypair.random();

pair.secret();
// SAV76USXIJOBMEQXPANUOQM6F5LIOTLPDIDVRJBFFE2MDJXG24TAPUU7
pair.publicKey();
// GCFXHS4GXL6BVUCXBWXGTITROWLVYXQKQLF4YH5O5JT3YZXCYPAFBJZB
```

```python
# stellar-sdk >= 2.0.0 required
# create a completely new and unique pair of keys
# see more about KeyPair objects: https://stellar-sdk.readthedocs.io/en/latest/api.html#keypair
from stellar_sdk import Keypair

pair = Keypair.random()
print(f"Secret: {pair.secret}")
# Secret: SCMDRX7A7OVRPAGXLUVRNIYTWBLCS54OV7UH2TF5URSG4B4JQMUADCYU
print(f"Public Key: {pair.public_key}")
# Public Key: GAG7SXULMNWCW6LX42JKZOZRA2JJXQT23LYY32OXA6XECUQG7RZTQJHO
```

</CodeExample>
````

Languages that are currently being used in Documentation and API Reference are
below:

```js
// https://github.com/stellar/stellar-docs/blob/main/src/components/CodeExample.js

const CODE_LANGS = {
  bash: 'bash',
  cpp: 'C++',
  curl: 'cURL',
  go: 'Go',
  html: 'html',
  java: 'Java',
  javascript: 'JavaScript',
  js: 'JavaScript',
  json: 'JSON',
  json5: 'JSON5',
  python: 'Python',
  scss: 'SCSS',
  toml: 'TOML',
  ts: 'TypeScript',
  tsx: 'TSX',
  typescript: 'TypeScript',
  yaml: 'YAML',
};
```

**Remember that this is a community; we build together! 🫱🏻‍🫲🏽 Our code of conduct is [here](https://www.stellar.org/community/code-of-conduct) and our Privacy Policy is [here](https://www.stellar.org/privacy-policy).**

[docs]: https://developers.stellar.org/docs
[api]: https://developers.stellar.org/api
[stellar]: https://stellar.org
[contrib]: https://github.com/stellar/.github/blob/master/CONTRIBUTING.md
[coc]: https://github.com/stellar/.github/blob/master/CODE_OF_CONDUCT.md
[docusaurus]: https://docusaurus.io
[mdx]: https://mdxjs.com
[commonmark]: https://commonmark.org/help/
[tutorial]: https://www.markdowntutorial.com/
[guide]: https://www.markdownguide.org/
[alert-example]: https://developers.stellar.org/docs/anchoring-assets/enabling-cross-border-payments/setting-up-test-server
[prism]: https://github.com/FormidableLabs/prism-react-renderer
[codespaces]: https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=521307729&machine=basicLinux32gb&devcontainer_path=.devcontainer%2Fdevcontainer.json&location=EastUs
[gitpod]: https://gitpod.io/#https://github.com/stellar/stellar-docs
