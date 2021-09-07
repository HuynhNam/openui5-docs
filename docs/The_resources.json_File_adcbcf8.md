<!-- loioadcbcf8b50924556ab3f321fcd9353ea -->

| loio |
| -----|
| adcbcf8b50924556ab3f321fcd9353ea |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/adcbcf8b50924556ab3f321fcd9353ea) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/adcbcf8b50924556ab3f321fcd9353ea)</div>

## The `resources.json` File

The `resources.json` file lists all resources in a component or library folder. It resides next to each `manifest.json` in the generated results.

The file is generated during build time, and its main purpose is for mobile packaging, as `resources.json` mentions all files inside the application.

If an app has a `resources.json` file, it is mentioned in the `manifest.json` under `sap.app/resources`.

> ### Note:  
> This file is used by SAP Tools like the SAP Fiori Client Packager. It will be generated automatically when using SAP Web IDE.

The list of resources is stored in an array in the `resources` property of the top level JSON object. The top level object can also contain the `_version` property, which can be omitted if the value is `1.0.0`. For each resource, the following entries are possible:


<table>
<tr>
<th>

Property



</th>
<th>

Type



</th>
<th>

Mandatory



</th>
<th>

Description



</th>
</tr>
<tr>
<td>

 `name` 



</td>
<td>

 `string` 



</td>
<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)



</td>
<td>

The relative path of the resource as accessible in a server. The path is relative to the location of the `resources.json` file, for example `Component.js`.



</td>
</tr>
<tr>
<td>

 `size` 



</td>
<td>

 `number` 



</td>
<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)



</td>
<td>

The size in bytes of the resource.



</td>
</tr>
<tr>
<td>

 `condRequired` 



</td>
<td>

 `string[]` 



</td>
<td>

 



</td>
<td>

A list of conditional dependencies of this resource. These dependencies can be required during execution of this resource.



</td>
</tr>
<tr>
<td>

 `designtime` 



</td>
<td>

 `boolean` 



</td>
<td>

 



</td>
<td>

When set to `true`, the resource is considered a designtime resource. The OpenUI5 build derives the flag from the naming convention \(could be `/designtime/`, `.designtime.js`, `.control`, `.interface`, `.type`, `.less`, `library.templates.xml`, `library.dependencies.xml`, or `library.dependencies.json`\).



</td>
</tr>
<tr>
<td>

 `dynRequired` 



</td>
<td>

 `boolean` 



</td>
<td>

 



</td>
<td>

When set to `true`, the resource has dynamic dependencies. The name of this dependency could not be resolved during build time.



</td>
</tr>
<tr>
<td>

 `exposedGlobalNames` 



</td>
<td>

 `string[]` 



</td>
<td>

 



</td>
<td>

A list of variables which are exposed to the global JS scope.



</td>
</tr>
<tr>
<td>

 `format` 



</td>
<td>

 `string` 



</td>
<td>

 



</td>
<td>

Defines the format of this resource; `raw` means that it is not a UI5 module.



</td>
</tr>
<tr>
<td>

 `included` 



</td>
<td>

 `string[]` 



</td>
<td>

 



</td>
<td>

List of sub-modules which are included in this resource, e.g. the `Component-preload.js` typically has the `included` property.



</td>
</tr>
<tr>
<td>

 `isDebug` 



</td>
<td>

 `boolean` 



</td>
<td>

 



</td>
<td>

When set to `true`, the resource is a debug source, the OpenUI5 build derives the flag from the naming convention \(`-dbg(.controller .view .fragment).js`\).



</td>
</tr>
<tr>
<td>

 `locale` 



</td>
<td>

 `string` 



</td>
<td>

 



</td>
<td>

Locale of the resource for known i18n resources; the OpenUI5 build derives the locale from the naming convention \(`*_[locale].properties`\).



</td>
</tr>
<tr>
<td>

 `merged` 



</td>
<td>

 `string` 



</td>
<td>

 



</td>
<td>

Indicates whether the resource is a merged resource. By default, the OpenUI5 build determines this from naming conventions \(`library-preload.json`, `library-all.js`, `Component-preload.js`\), but it also allows to add more merged files by manual configuration of the build step. SAP Web IDE may use other knowledge for this; it knows, for example, that it merges the`Component-preload.js`.



</td>
</tr>
<tr>
<td>

 `module` 



</td>
<td>

 `string` 



</td>
<td>

 



</td>
<td>

The name of the UI5 module, including the file extension.



</td>
</tr>
<tr>
<td>

 `raw` 



</td>
<td>

 `string` 



</td>
<td>

 



</td>
<td>

The name of the corresponding resource in the raw \(developer\) language for known i18n resources; for example, for`messagebundle.en.properties`, the corresponding raw file is `messagebundle.properties`.



</td>
</tr>
<tr>
<td>

 `required` 



</td>
<td>

 `string[]` 



</td>
<td>

 



</td>
<td>

A list of dependencies of this resource. These dependencies are required prior to using this resource.



</td>
</tr>
<tr>
<td>

 `support` 



</td>
<td>

 `boolean` 



</td>
<td>

 



</td>
<td>

When set to `true`, the resource is considered a ssupport assistant resource.

The OpenUI5 build derives this flag from the naming convention `.support.js`.



</td>
</tr>
<tr>
<td>

 `theme` 



</td>
<td>

 `string` 



</td>
<td>

 



</td>
<td>

Indicates a theme-dependent resource.

The OpenUI5 build determines this from the naming convention `**themes/<theme>/**`



</td>
</tr>
</table>

***

``` js

{
    "resources": [
        {
            "name": ".library",
            "size": 473
        },
        {
            "name": ".theming",
            "size": 368
        },
        },
        {
            "name": "Component-preload.js",
            "module": "application/mine/Component-preload.js",
            "size": 361,
            "merged": true,
            "included": [
                "application/mine/Component.js",
                "application/mine/TodoComponent.js"
            ],
            "dynRequired": true,
            "condRequired": [
                "sap/m/MessageBox.js"
            ],
            "required": [
                "sap/base/Log.js"
            ]
        },
        {
            "name": "DynamicSideContent-dbg.js",
            "module": "application/mine/DynamicSideContent.js",
            "isDebug":true,
            "size": 115
        },
        {
            "name": "DynamicSideContent.js",
            "module": "application/mine/DynamicSideContent.js",
            "size": 78
        },
        {
            "name": "DynamicSideContentRenderer-dbg.js",
            "module": "application/mine/DynamicSideContentRenderer.js",
            "isDebug":true,
            "size": 110,
            "required": [
                "sap/ui/core/UIComponent.js"
            ]
        },
 
        ...
 
        {
            "name": "library-preload.json",
            "module": "application/mine/library-preload.json",
            "merged":true,
            "size": 294
        },

        ...

        {
            "name": "designtime/library.designtime.js",
            "module": "application/mine/designtime/library.designtime.js",
            "size": 84,
            "designtime": true
        },
 
        ...
 
        {
            "name": "messagebundle_de.properties",
            "module": "application/mine/i18n/messagebundle_de.properties",
            "raw":"messagebundle.properties",
            "locale":"de",
            "size": 163,
        },
 
        ...
 
        {
            "name": "themes/sap_belize/library.less",
            "theme":"sap_belize",
            "size": 311,
            "designtime": true
        }
 
        ...
        {
            "name": "plugin/LessSupport-dbg.js",
            "module": "sap/ui/core/plugin/LessSupport.js",
            "condRequired": [
                "sap/ui/core/theming/Parameters.js",
                "sap/ui/thirdparty/less.js"
            ],
            "exposedGlobalNames": ["globalLess"],
            "dynRequired": true,
            "format": "raw",
            "isDebug": true,
            "size": 18494
        }

        ...

        {
            "name": "resources.json",
            "dynRequired": true,
            "size": 1000000
        }
    ]
}
```

