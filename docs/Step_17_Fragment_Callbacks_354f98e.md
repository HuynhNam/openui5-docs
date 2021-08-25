<!-- loio354f98ed2b514ba9960556333428d35e -->

| loio |
| -----|
| 354f98ed2b514ba9960556333428d35e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/354f98ed2b514ba9960556333428d35e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/354f98ed2b514ba9960556333428d35e)</div>

## Step 17: Fragment Callbacks

Now that we have integrated the dialog, it's time to add some user interaction. The user will definitely want to close the dialog again at some point, so we add a button to close the dialog and assign an event handler.

***

### Preview

   
  
<a name="loio354f98ed2b514ba9960556333428d35e__fig_r1j_pst_mr"/>The dialog now has an "OK" button

 ![](loio2a0aee6164b24340b0d34a0515c82f19_HiRes.png "The dialog now has an "OK" button") 

***

### Coding

You can view and download all files at [Walkthrough - Step 17](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.17/preview).

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/m/MessageToast",
	"sap/ui/core/Fragment"
], function (Controller, MessageToast, Fragment) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.HelloPanel", {

		onShowHello : function () {
			// read msg from i18n model
			var oBundle = this.getView().getModel("i18n").getResourceBundle();
			var sRecipient = this.getView().getModel().getProperty("/recipient/name");
			var sMsg = oBundle.getText("helloMsg", [sRecipient]);

			// show message
			MessageToast.show(sMsg);
		},

		onOpenDialog : function () {
			var oView = this.getView();

			if (!this.pDialog) {
				this.pDialog = Fragment.load({
					id: oView.getId(),
					name: "sap.ui.demo.walkthrough.view.HelloDialog"*HIGHLIGHT START*,
					controller: this*HIGHLIGHT END*
				}).then(function (oDialog) {
					// connect dialog to the root view of this component (models, lifecycle)
					oView.addDependent(oDialog);
					return oDialog;
				});
			} 
			this.pDialog.then(function(oDialog) {
				oDialog.open();
			});
		}*HIGHLIGHT START*,

		onCloseDialog : function () {
			// note: We don't need to chain to the pDialog promise, since this event-handler
			// is only called from within the loaded dialog itself.
			this.byId("helloDialog").close();
		}*HIGHLIGHT END*
	});

});
```

As previously described, fragments are pure UI reuse artifacts and do not have a controller. However, you can pass a controller object to the `Fragment.load` API. For our dialog we reference the `HelloPanel` controller. However, the third parameter does not necessarily have to be a controller but can be any object. Just don't forget the `this` keyword.

The event handler function is put into the same controller file and it closes the dialog by accessing the internal helper function that returns the dialog.

***

### webapp/view/HelloDialog.fragment.xml

``` xml
<core:FragmentDefinition
   xmlns="sap.m"
   xmlns:core="sap.ui.core" >
   <Dialog
      id="helloDialog"
      title ="Hello {/recipient/name}">
*HIGHLIGHT START*      <beginButton>
         <Button
            text="{i18n>dialogCloseButtonText}"
            press=".onCloseDialog"/>
      </beginButton>*HIGHLIGHT END*
   </Dialog>
</core:FragmentDefinition>
```

In the fragment definition, we add a button to the `beginButton` aggregation of the dialog. The press handler is referring to an event handler called `.onCloseDialog`, and since we passed in the reference to the `HelloPanel` controller, the method will be invoked there when the button is pressed. The dialog has an aggregation named `beginButton` as well as `endButton`. Placing buttons in both of these aggregations makes sure that the `beginButton` is placed before the `endButton` on the UI. What `before` means, however, depends on the text direction of the current language. We therefore use the terms `begin` and `end` as a synonym to “left” and “right". In languages with left-to-right direction, the `beginButton` will be rendered left, the `endButton` on the right side of the dialog footer; in right-to-left mode for specific languages the order is switched.

***

<a name="loio354f98ed2b514ba9960556333428d35e__section_d5m_ypr_r2b"/>

### webapp/i18n/i18n.properties

``` prefs
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}
homePageTitle=Walkthrough
helloPanelTitle=Hello World
openDialogButtonText=Say Hello With Dialog
*HIGHLIGHT START*dialogCloseButtonText=Ok*HIGHLIGHT END*
```

The text bundle is extended by the new text for the dialog’s close button.

**Related Information**  


[Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md "Fragments are light-weight UI parts (UI sub-trees) which can be reused, defined similar to views, but do not have any controller or other behavior code involved.")

[Instantiation of Fragments](Instantiation_of_Fragments_04129b2.md "OpenUI5 provides two options to instantiate a fragment: If it is instantiated inside a controller extending sap.ui.core.mvc.Controller, the loadFragment() function is the way to go. However, if it is instantiated in a non-controller artefact, the generic function sap.ui.core.Fragment.load() can be used.")

