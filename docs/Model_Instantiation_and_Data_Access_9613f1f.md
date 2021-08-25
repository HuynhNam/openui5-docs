<!-- loio9613f1f2d88747cab21896f7216afdac -->

| loio |
| -----|
| 9613f1f2d88747cab21896f7216afdac |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9613f1f2d88747cab21896f7216afdac) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9613f1f2d88747cab21896f7216afdac)</div>

## Model Instantiation and Data Access

One OData V4 model instance can only cover one OData service. This section describes the creation of a model instance in more detail.

The OData V4 model is primarily designed for OData V4 services. Nevertheless, OData V2 services may be used through an adapter as well. For more information see: [Consuming OData V2 Services with the OData V4 Model](Consuming_OData_V2_Services_with_the_OData_V4_Model_365bdbd.md)

When creating an OData V4 model instance, the only parameter you actually need is a map. This map must contain at least the properties `serviceUrl` and `synchronizationMode`. For more information, see the [sap.ui.model.odata.v4.ODataModel constructor](https://openui5.hana.ondemand.com/docs/api/symbols/sap.ui.model.odata.v4.ODataModel.html#constructor) API documentation in the Demo Kit.

**OData V4 model instantiation:**

``` js

sap.ui.define(["sap/ui/model/odata/v4/ODataModel"], function (ODataModel) {
    var oModel = new ODataModel({
        serviceUrl : "/sap/opu/odata4/IWBEP/V4_SAMPLE/default/IWBEP/V4_GW_SAMPLE_BASIC/0001/",
        synchronizationMode : "None"
    });
});
```

***

### OData Custom Query Options

An OData service accepts query options placed in the service URL query part, as explained on the URL conventions page [OData Version 4.0 Part 2: URL Conventions](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part2-url-conventions.html) in chapter 2 *URL Components*. The OData V4 model accepts OData custom query options only as explained in section 5.2 *Custom Query Options* of the URL conventions page; you must not provide OData system query options \(starting with "$"\) or OData parameter aliases \(starting with "@"\) at model level, see sections 5.1 *System Query Options* and 5.3 *Parameter Aliases* in the URL conventions page.

> ### Note:  
> Note that it's possible to specify certain system query options for OData V4 model bindings. For more information, see [Bindings](Bindings_54e0ddf.md).

**OData V4 model instantiation with service URL parameters:**

``` js

sap.ui.define(["sap/ui/model/odata/v4/ODataModel"], function (ODataModel) {
    var oModel = new ODataModel({
    	serviceUrl : "/sap/opu/odata4/IWBEP/V4_SAMPLE/default/IWBEP/V4_GW_SAMPLE_BASIC/0001/?customParam=foo", 
    	synchronizationMode : "None"
    });
});
```

***

### Default Groups for Batch Control

The OData V4 model allows you to specify whether or not requests are bundled and sent as a batch request, and when the requests are sent. For more information, see [Batch Control](Batch_Control_74142a3.md).

The parameter `groupId` specifies the default batch group and defaults to `"$auto"`. You can use the parameter `updateGroupId` to set a batch group for update requests only. If you do not set this parameter, the `groupId` will be used.

The following code instantiates a model that bundles all update requests in the batch group `"myAppUpdateGroup"`; the batch request can then be sent using `oModel.submitBatch("myAppUpdateGroup")`.

**OData V4 model with `updateGroupId`:**

``` js

sap.ui.define(["sap/ui/model/odata/v4/ODataModel"], function (ODataModel) {
    var oModel = new ODataModel({
        serviceUrl : "/sap/opu/odata4/IWBEP/V4_SAMPLE/default/IWBEP/V4_GW_SAMPLE_BASIC/0001/",
        synchronizationMode : "None",
        updateGroupId : "myAppUpdateGroup"
    });
});
```

***

### Instantiating an OData V4 Model Using the Descriptor File \(`manifest.json`\)

The code sample below shows the parts of a [Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md) \(`manifest.json`\) that are relevant for instantiating an OData V4 model:

``` js

{
    "sap.app" : {
        "dataSources" : {
            "default" : {
                "uri" : "/sap/opu/odata4/IWBEP/V4_SAMPLE/default/IWBEP/V4_GW_SAMPLE_BASIC/0001/",
                "type" : "OData",
                "settings" : {
                    "odataVersion" : "4.0"
                }
            }
        }
    },
    "sap.ui5" : {
        "models" : {
            "" : {
                "dataSource" : "default",
                "settings" : {
                    "synchronizationMode" : "None",
                    "updateGroupId" : "myAppUpdateGroup"
                }
            }
        }
    }
}
```

***

### Data Access

The OData V4 model only supports data access using bindings. It does not provide any direct access to the data. For more information, see [Unsupported Superclass Methods and Events](Unsupported_Superclass_Methods_and_Events_1232241.md). One exception is [sap.ui.model.odata.v4.Context\#setProperty](https://openui5.hana.ondemand.com/#/api/symbols/sap.ui.model.odata.v4.Context/methods/setProperty). It allows to update a property without using a property binding, even without reading the data first. You can create bindings that are independent of controls. For more information, see [Accessing Data in Controller Code](Accessing_Data_in_Controller_Code_17b30ac.md).

***

### Language

OpenUI5 uses the concept of a "current language" \(see [Identifying the Language Code / Locale](Identifying_the_Language_Code__Locale_91f21f1.md)\). This language is automatically propagated to the OData service by the OData V4 model. For this reason, applications must not hard code the language themselves, e.g. they must not specify the `"sap-language"` URL parameter as a custom query option.

***

<a name="loio9613f1f2d88747cab21896f7216afdac__section_oyf_bpb_fjb"/>

### Set HTTP Header Fields

You can set headers for HTTP requests sent by the OData V4 model: This is possible statically by adding them to the `manifest.json`, or dynamically with the method [ODataModel\#changeHttpHeaders](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel). These headers are applied to data and metadata requests sent by the model. The `ODataModel` propagates its HTTP headers to value list models created via [ODataMetaModel\#createValueListInfo](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel); when changing HTTP headers for the model, however, these changes are not applied to existing value list models: If value list models require the new headers, you have to additionally call `ODataModel#changeHttpHeaders` for each of them. For details, see [ODataModel\#changeHttpHeaders](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel).

Sample: Set HTTP header `custom` in manifest.json:

``` js
{
    "sap.app" : {
        "dataSources" : {
            "default" : {
                "uri" : "/sap/opu/odata4/IWBEP/V4_SAMPLE/default/IWBEP/V4_GW_SAMPLE_BASIC/0001/",
                "type" : "OData",
                "settings" : {
                    "odataVersion" : "4.0"
                }
            }
        }
    },
    "sap.ui5" : {
        "models" : {
            "" : {
                "dataSource" : "default",
                "settings" : {
                    "autoExpandSelect" : true,
                    "httpHeaders" : {
                        "custom" : "foo"
                    },
                    "synchronizationMode" : "None",
                     
                }
            }
        }
    }
}

```

**Related Information**  


[Constructor: sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/docs/api/symbols/sap.ui.model.odata.v4.ODataModel.html#constructor)

[OData Version 4.0 Part 2: URL Conventions](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part2-url-conventions.html)

[Bindings](Bindings_54e0ddf.md "Bindings connect OpenUI5 view elements to model data, allowing changes in the model to be reflected in the view element and vice versa.")

[Batch Control](Batch_Control_74142a3.md "OData V4 allows you to group multiple operations into a single HTTP request payload, as described in the official OData V4 specification Part 1, Batch Requests (see the link under Related Information for more details).")

[Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md "The descriptor for applications, components, and libraries (in short: app descriptor) is inspired by the WebApplication Manifest concept introduced by the W3C. The descriptor provides a central, machine-readable, and easy-to-access location for storing metadata associated with an application, an application component, or a library.")

[Unsupported Superclass Methods and Events](Unsupported_Superclass_Methods_and_Events_1232241.md "Certain methods derived from OpenUI5 model and binding superclasses are not supported in OData V4 model classes or have limited support.")

