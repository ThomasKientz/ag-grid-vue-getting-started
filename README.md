# Ag-grid-vue getting started

## Add ag-Grid to Your Project

### Install npm dependencies

> npm install --save @ag-grid-community/vue @ag-grid-enterprise/all-modules vue-property-decorator

### Importer licence

```javascript
// main.js
import { LicenseManager } from "@ag-grid-enterprise/core";

LicenseManager.setLicenseKey("LicenceKey");
```

### Import styles

Depending on the project configuration, insert the next following code either in a `.scss` file imported by `main.js` or inside a style's tag in `App.vue` as following :

```html
// App.vue
<style lang="scss">
  ... //scss
</style>
```

```scss
// scss
// examples of overriding sass variables
$ag-cell-horizontal-padding: 5px;
$ag-tool-panel-background-color: #fff;
$ag-primary-color: #ea6919;
$ag-accent-color: #2196f3;

@import "~@ag-grid-enterprise/all-modules/dist/styles/ag-grid.scss";
@import "~@ag-grid-enterprise/all-modules/dist/styles/ag-theme-material/sass/ag-theme-material.scss";
```

## Usage in a vue component

Template :

```html
<ag-grid-vue
  style="width: 500px; height: 500px;"
  class="ag-theme-material"
  :modules="modules"
  :columnDefs="columnDefs"
  :rowData="rowData"
>
</ag-grid-vue>
```

Javascript :

```javascript
import { AgGridVue } from "ag-grid-vue";
import { AllModules } from "@ag-grid-enterprise/all-modules";

export default {
  components: {
    AgGridVue
  },
  data() {
    return {
      columnDefs: null,
      rowData: null,
      modules: AllModules
    };
  },
  beforeMount() {
    this.columnDefs = [
      { headerName: "Make", field: "make" },
      { headerName: "Model", field: "model" },
      { headerName: "Price", field: "price" }
    ];

    this.rowData = [
      { make: "Toyota", model: "Celica", price: 35000 },
      { make: "Ford", model: "Mondeo", price: 32000 },
      { make: "Porsche", model: "Boxter", price: 72000 }
    ];
  }
};
```

## Resources

[Ag-grid Vue documentation](https://www.ag-grid.com/vuejs-grid/) (out of date)
