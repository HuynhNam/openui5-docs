<!-- loio79e910e6a0d949c7acb051b33170bebc -->

| loio |
| -----|
| 79e910e6a0d949c7acb051b33170bebc |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/79e910e6a0d949c7acb051b33170bebc) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/79e910e6a0d949c7acb051b33170bebc)</div>

## Use Stable IDs

If you keep the IDs of controls, elements, and components stable, you can be sure that other OpenUI5 features will be able to identify them correctly during processing.

***

<a name="loio79e910e6a0d949c7acb051b33170bebc__section_gtm_xlp_3z"/>

### Background

OpenUI5generates IDs for controls, elements, or components dynamically if you don't set them yourself. This sounds convenient, but might lead to problems when the corresponding elements are processed later on by other OpenUI5 features. So it's a good idea to use stable IDs instead of dynamic IDs.

***

<a name="loio79e910e6a0d949c7acb051b33170bebc__section_k23_b5s_rkb"/>

### How to Make IDs Stable

For this, you use the `id` property or attribute of the respective element. For a list of the elements for which you can set stable ID, see the related link below.

Here's an example of an XML view **without** stable IDs:

``` xml
<mvc:View
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Page>
		<content>
			<Table>
			</Table>
		</content>
	</Page>
</mvc:View>

```

At runtime, the `Page` and the `Table` would get dynamically generated IDs like `__page0` and `__table0`. However, these generated IDs can change whenever the control structure of the app changes.

If you define stable IDs for the two controls in the example above, it could look like this:

``` js
<mvc:View
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Page *HIGHLIGHT START*id="page"*HIGHLIGHT END*>
		<content>
			<Table *HIGHLIGHT START*id="table"*HIGHLIGHT END*>
			</Table>
		</content>
	</Page>
</mvc:View>

```

The controls will now always be identified by these IDs.

In the case of views, the sequence of instantiation also plays a role: If there are two views with unstable IDs in the app, they get the generated IDs `__view0` and `__view1` depending on the order the views are opened. This makes it impossible to correctly identify them when they are processed by other features.

> Note:
> You should choose a semantic name for your IDs that makes it easier for you to identify them later.
> 
> 

For more information about naming restrictions, some testing options to check for unstable IDs, as well as the features that require stable IDs, see the related link below.

**Related information**  


[Stable IDs: All You Need to Know](Stable_IDs_All_You_Need_to_Know_f51dbb7.md)
