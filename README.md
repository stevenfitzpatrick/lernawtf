# Lerna Package structure

### Every Component is a package

In the "consumer" react website

```javascript
import Button from "@swrve/Button"
import LinkButton from "@swrve/LinkButton"
import IconButton from "@swrve/IconButton"
import Input from "@swrve/Input"
import TextArea from "@swrve/Textarea"
import Select from "@swrve/Select"
import Table from "@swrve/Table"
import SortTable from "@swrve/SortTable"
```

In the "consumer" package.json

```javascript
  "devDependencies": {
    "@swrve/Button": "^1.8.2",
    "@swrve/LinkButton": "^2.1.0",
    "@swrve/IconButton": "^2.1.0",
    "@swrve/Input": "^2.9.1",
    "@swrve/Textarea": "^1.0.9",
    "@swrve/Select": "^16.3.0",
    "@swrve/Table": "^16.3.0"
    "@swrve/SortTable": "^16.3.0"
  }
```

Samples :

* Babel (https://github.com/babel/babel/)

### Group Components into logical bundles

In the "consumer" react website

```javascript
import { Button, LinkButton, IconButton, Input, TextArea } from "@swrve/core"
import { Select } from "@swrve/select"
import { Table, SortTable } from "@swrve/table"
```

In the "consumer" package.json

```javascript
  "devDependencies": {
    "@swrve/core": "^1.8.2",
    "@swrve/select": "^2.1.0",
    "@swrve/table": "^2.1.0",
  }
```

Samples :

* Blueprint UI Lib (https://github.com/palantir/blueprint)

### Single UI Library

```javascript
import {
  Button,
  LinkButton,
  IconButton,
  Input,
  TextArea,
  Select,
  Table,
  SortTable
} from "@swrve/ui"
```

In the "consumer" package.json

```javascript
  "devDependencies": {
    "@swrve/ui": "^1.8.2",
  }
```

Samples (Not Lerna) :

* React Bootstrap (https://github.com/reactstrap/reactstrap)
* Remove Unused imports (https://github.com/GoogleChromeLabs/webpack-libs-optimizations#react-bootstrap)

# Lerna Versioning

### Independent

* https://github.com/apollographql/apollo-client (Independent)

### Fixed

* https://github.com/babel/babel (Babel)
* https://github.com/storybooks/storybook (Storybook)

### Conventional Commits

* https://conventionalcommits.org/ (Commit Convention)

  * perf,fix (Path) i.e 1.0.**1**

  ```javascript
  fix: resolve webpack path issue for components
  fix(Webpack): resolve webpack path issue for components
  perf(JIRA-1234): resolve webpack path issue for components
  ```

  * feat (Minor) 1.**1**.1

  ```javascript
  feat(TextArea): Adding TextArea component
  ```

  * BREAKING CHANGE (Breaking) **2**.0.0

  ```javascript
  feat(Tables): Adding new table with new depedency
    BREAKING CHANGE: New Depedency added react-tables
  ```

#### Why ?

* Automatically generating CHANGELOGs.
* Automatically determining a semantic version bump (based on the types of commits landed).
* Communicating the nature of changes to teammates, the public, and other stakeholders.

#### Examples

* StyleGuidist (https://github.com/styleguidist/react-styleguidist/commits/master)
* Yargs (https://github.com/yargs/yargs/commits/master)
* Standard Version (https://github.com/conventional-changelog/standard-version/commits/master)
