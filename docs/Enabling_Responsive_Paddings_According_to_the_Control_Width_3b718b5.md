<!-- loio3b718b5372fa457c92cf5087a673e953 -->

| loio |
| -----|
| 3b718b5372fa457c92cf5087a673e953 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3b718b5372fa457c92cf5087a673e953) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3b718b5372fa457c92cf5087a673e953)</div>

## Enabling Responsive Paddings According to the Control Width

Apply responsive paddings over separate parts of the controls.

> ### Note:  
> You can enable the responsive paddings based on the with of the control only for the SAP Quartz themes.

***

<a name="loio3b718b5372fa457c92cf5087a673e953__section_d2f_1pv_jjb"/>

### Usage

Application developers can now apply responsive paddings over separate parts of the controls and align the space distribution properly, according to the width of the control \(and not the whole screen\). This can be done by using a set of classes, which are available for the different controls.

***

#### Applied Paddings

Based on the container’s size, one of the following classes is added, and the corresponding padding-left and padding-right are applied:


<table>
<tr>
<th>

Container Size \(pixels\)



</th>
<th>

Class



</th>
<th>

Padding-Left and Padding-Right Applied



</th>
</tr>
<tr>
<td>

<= 600



</td>
<td>

sapUi-Std-PaddingS



</td>
<td>

1rem



</td>
</tr>
<tr>
<td>

\>600



</td>
<td>

sapUi-Std-PaddingM



</td>
<td>

2rem



</td>
</tr>
<tr>
<td>

\>1024



</td>
<td>

sapUi-Std-PaddingL



</td>
<td>

2rem



</td>
</tr>
<tr>
<td>

\>1440



</td>
<td>

sapUi-Std-PaddingXL



</td>
<td>

3rem



</td>
</tr>
</table>

***

#### Supported Controls

The following table shows the controls that support responsive paddings. To enable this concept and to add responsive paddings to an element of the controls, add the corresponding classes to the controls, depending on your use case:


<table>
<tr>
<th>

Supported Controls



</th>
<th>

 `sapUiResponsivePadding--header` 



</th>
<th>

 `sapUiResponsivePadding--subHeader` 



</th>
<th>

 `sapUiResponsivePadding--content` 



</th>
<th>

 `sapUiResponsivePadding--footer` 



</th>
<th>

 `sapUiResponsivePadding--floatingFooter` 



</th>
</tr>
<tr>
<td>

`sap.m.Dialog`

\(`sap.m.MessageBox`,

`sap.m.SelectDialog`,

`sap.m.TableSelectDialog`\)



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 `sap.m.IconTabBar` 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 `sap.m.ObjectHeader` 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 `sap.m.Page` 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 `sap.m.Popover` 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 `sap.m.TabContainer` 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 `sap.m.Wizard` 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
</table>

> ### Note:  
> If nessecary, you can further align controls by using the available set of predefined CSS margin classes. For example, you can add negative margins to an element on its left and right sides. For more information, see [Using Predefined CSS Margin Classes](Using_Predefined_CSS_Margin_Classes_777168f.md).

***

```
<Page class="sapUiResponsivePadding--header sapUiResponsivePadding--subHeader sapUiResponsivePadding--content sapUiResponsivePadding--footer sapUiResponsivePadding--floatingFooter">
```

For a detailed example, see the [Samples for `sap.m.Page`](https://openui5.hana.ondemand.com/#/entity/sap.m.Page). 

***

***

#### How to Enable Responsive Paddings

As a control developer, you can enable application developers to apply responsive paddings, by implementing the `sap.ui.core.util.ResponsivePaddingsEnablement` utility.

Here is an example:

```
ResponsivePaddingsEnablement.call(MyCustomControl.prototype, {
					header: {suffix: "-myCustomControlHeader"},
					content: {selector: ".myCustomControlContent"}
					});
				
```

As the example demonstrates, there are two ways to select an element:

-   Using suffix: This enables you to select an element by its ID.
-   Using selector: This covers all possible CSS selections.

To call the utility, when initializing the control, use:

```
MyCustomControl._initResponsivePaddingsEnablement()
```

As a result, application developers will be able to use classes, such as `sapUiResponsivePadding—header` and `sapUiResponsivePadding--content`, to enable the paddings on the respective element.

