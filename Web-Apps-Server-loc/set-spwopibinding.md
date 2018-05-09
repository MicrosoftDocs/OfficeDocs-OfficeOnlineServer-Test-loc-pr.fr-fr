---
title: Set-SPWOPIBinding
TOCTitle: Set-SPWOPIBinding
ms:assetid: e373528f-e69b-4e25-9df4-3a5f80ab64ac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219454(v=office.15)
ms:contentKeyID: 49645244
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIBinding

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2015-03-09_

Met à jour l'action de clic par défaut pour la liaison à une application ou à une extension de nom de fichier.

## Syntaxe

    Set-SPWOPIBinding [-Identity] <SPWopiBindingPipeBind> -DefaultAction <SwitchParameter> [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **Set-SPWOPIBinding** met à jour l'action de clic par défaut pour la liaison à une application ou à une extension de nom de fichier. Par exemple, vous pouvez définir l'action de clic par défaut pour afficher un document Word dans une bibliothèque SharePoint. Pour ce faire, vous affectez à l'action par défaut la valeur true pour la liaison “view”-“Word”.

En général, vous utilisez la sortie de la commande **Get-SPWOPIBinding** comme valeur pour la propriété -Identity de cette commande. Pour plus d’informations, voir [Get-SPWOPIBinding](get-spwopibinding.md)

<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous pouvez uniquement définir des liaisons créées à l’aide de la commande <strong>New-SPWOPIBinding</strong>. Pour remplacer une liaison intégrée, par exemple, l’action menée lors de l’affichage d’un document Word dans une bibliothèque SharePoint, créez une liaison, à l’aide de <strong>New-SPWOPIBinding</strong>, et affectez une autre action. Pour plus d’informations, voir <a href="new-spwopibinding.md">New-SPWOPIBinding</a>.</td>
</tr>
</tbody>
</table>


SharePoint Management Shell

## Paramètres


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Obligatoire</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identité</strong></p></td>
<td><p>Obligatoire</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Spécifie la liaison. En général, vous utilisez la sortie de la commande <strong>Get-SPWOPIBinding</strong> comme valeur pour –Identity.</p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultAction</strong></p></td>
<td><p>Obligatoire</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Spécifie si la liaison Set-SPWOPIBinding doit être définie comme l'action de clic par défaut pour une application ou une extension de nom de fichier dans la liaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Gère les objets de manière à optimiser leur libération. L’utilisation d’objets, tels que <strong>SPWeb</strong> ou <strong>SPSite</strong>, peut consommer des quantités de mémoire élevées et le recours à ces objets dans des scripts Windows PowerShell implique une gestion appropriée de la mémoire. À l’aide de l’objet <strong>SPAssignment</strong>, vous pouvez affecter des objets à une variable et les libérer dès qu’ils ne sont plus nécessaires afin de libérer de la mémoire. Lorsque les objets <strong>SPWeb</strong>, <strong>SPSite</strong> ou <strong>SPSiteAdministration</strong> sont utilisés, ils sont automatiquement libérés si un ensemble d’affectations ou si le paramètre <strong>Global</strong> n’est pas utilisé.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lorsque le paramètre <strong>Global</strong> est utilisé, tous les objets sont contenus dans le magasin global. Si des objets ne sont pas utilisés immédiatement ou libérés à l’aide de la commande <strong>Stop-SPAssignment</strong>, un scénario d’insuffisance de mémoire peut se produire.</td>
</tr>
</tbody>
</table>

</div>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Affiche un message qui explique l’effet de la commande au lieu de l’exécuter. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\--------------EXEMPLE-----------------

    Get-SPWOPIBinding -Action "view" -Application "Word"| Set-SPWOPIBinding -DefaultAction

Cet exemple montre comment définir l'action de clic par défaut pour afficher un document Word dans une bibliothèque SharePoint. Vous pouvez vérifier que l'action de clic par défaut est définie pour afficher Word en exécutant la cmdlet **Get-SPWOPIBinding –Action “view” –Application “Word”**. **IsDefaultAction** a la valeur « True ».

## Voir aussi


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  
[New-SPWOPIBinding](new-spwopibinding.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Office Web Apps avec SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

