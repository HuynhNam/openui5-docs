<!-- loiob229914587444025be986d81dcc77303 -->

| loio |
| -----|
| b229914587444025be986d81dcc77303 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b229914587444025be986d81dcc77303) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b229914587444025be986d81dcc77303)</div>

## Descriptor for Libraries

The descriptor for libraries contains a subset of the attributes in the descriptor for applications and components.


<table>
<tr>
<th>

manifest.json



</th>
<th>

.library



</th>
<th>

Available for SAPUI5 dist libraries?



</th>
<th>

Comment



</th>
</tr>
<tr>
<td>

 `sap.app/id` 



</td>
<td>

 `name` 



</td>
<td>

x



</td>
<td>



</td>
</tr>
<tr>
<td>

 `sap.app/type` 



</td>
<td>

-



</td>
<td>

x



</td>
<td>

Generated with value `library` 



</td>
</tr>
<tr>
<td>

 `sap.app/embeds` 



</td>
<td>

-



</td>
<td>

x



</td>
<td>

Generated



</td>
</tr>
<tr>
<td>

 `sap.app/i18n` 



</td>
<td>

 `appData/manifest/i18n` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.app/applicationVersion/version` 



</td>
<td>

 `version` 



</td>
<td>

x



</td>
<td>



</td>
</tr>
<tr>
<td>

 `sap.app/title` 



</td>
<td>

 `title` 



</td>
<td>

x



</td>
<td>

Text symbol syntax with leading curly brackets \(`{{`\) and trailing curly brackets \(`}}`\); new in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.app/description` 



</td>
<td>

 `documentation` 



</td>
<td>

x



</td>
<td>

Text symbol syntax with leading curly brackets \(`{{`\) and trailing curly brackets \(`}}`\)



</td>
</tr>
<tr>
<td>

 `sap.app/ach` 



</td>
<td>

 `appData/ownership/component` 



</td>
<td>

x



</td>
<td>



</td>
</tr>
<tr>
<td>

 `sap.app/openSourceComponents` 



</td>
<td>

 `appData/manifest/openSourceComponents` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.app/resources` 



</td>
<td>

-



</td>
<td>

x



</td>
<td>

Generated with value `resources.json` 



</td>
</tr>
<tr>
<td>

 `sap.app/offline` 



</td>
<td>

 `appData/manifest/offline` 



</td>
<td>

x



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.app/sourceTemplate` 



</td>
<td>

 `appData/manifest/sourceTemplate` 



</td>
<td>



</td>
<td>

New in `.library`, to be filled by SAP Web IDE only



</td>
</tr>
<tr>
<td>

 `sap.ui/technology` 



</td>
<td>

-



</td>
<td>

x



</td>
<td>

Generated with value `UI5` 



</td>
</tr>
<tr>
<td>

 `sap.ui/deviceTypes` 



</td>
<td>

 `appData/manifest/deviceTypes` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.ui/supportedThemes` 



</td>
<td>

-



</td>
<td>

x



</td>
<td>

Generated and merged



</td>
</tr>
<tr>
<td>

 `sap.ui5/dependencies/minUI5Version` 



</td>
<td>

-



</td>
<td>

x



</td>
<td>

Generated



</td>
</tr>
<tr>
<td>

 `sap.ui5/dependencies/libs` 



</td>
<td>

 `dependencies` 



</td>
<td>

x



</td>
<td>



</td>
</tr>
<tr>
<td>

 `sap.ui5/contentDensities` 



</td>
<td>

 `appData/manifest/contentDensities` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.platform.abap/uri` 



</td>
<td>

 `appData/manifest/sap.platform.abap/uri` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.platform.hcp/uri` 



</td>
<td>

 `appData/manifest/sap.platform.hcp/uri` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.fiori/registrationIds` 



</td>
<td>

 `appData/manifest/sap.fiori/registrationId` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
<tr>
<td>

 `sap.fiori/archeType` 



</td>
<td>

 `appData/manifest/sap.fiori/archeType` 



</td>
<td>



</td>
<td>

New in `.library` 



</td>
</tr>
</table>

**Related Information**  


[Creating a Descriptor File for Existing Apps](Creating_a_Descriptor_File_for_Existing_Apps_3a9baba.md "Detailed description of the steps needed to create a descriptor V2 for applications file for an existing transactional app created by the customer based on SAP Fiori.")

