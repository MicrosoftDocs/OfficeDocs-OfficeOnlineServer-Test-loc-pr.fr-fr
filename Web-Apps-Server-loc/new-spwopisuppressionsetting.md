---
title: New-SPWOPISuppressionSetting
TOCTitle: New-SPWOPISuppressionSetting
ms:assetid: 7e6bb8f5-3124-4568-80c6-02cae46b803b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219443(v=office.15)
ms:contentKeyID: 49645214
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPISuppressionSetting

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2015-03-09_

La cmdlet **New-SPWOPISuppressionSetting** désactive l'Office Web Apps pour l'action, l'extension de nom de fichier ou l'identificateur programmatique que vous avez spécifiés sur la batterie de serveurs SharePoint actuelle.

## Syntaxe

    New-SPWOPISuppressionSetting [-Action <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **New-SPWOPISuppressionSetting** désactive l'Office Web Apps pour l'action, l'extension de nom de fichier ou l'identificateur programmatique (ProgId) que vous avez spécifiés sur la batterie de serveurs SharePoint actuelle. La cmdlet procède à cette opération sans supprimer les informations de découverte ni la capacité des utilisateurs à se servir de la fonctionnalité de lien du partage SharePoint pour envoyer un lien vers un document et permettre au destinataire d'utiliser l'Office Web Apps pour ce type de document. Vous pouvez recourir à cette cmdlet si vous voulez utiliser Excel Services pour afficher les classeurs Excel à la place de l'application WOPI (par exemple l'Office Web Apps Server).

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
<td><p><strong>Action</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'action permettant de supprimer une extension donnée ou un identificateur programmatique (ProgId). Par exemple, « afficher », « modifier » et « afficher en mode incorporé ». Pour obtenir une liste complète des actions, exécutez <strong>Get-SPWOPIBinding</strong>.</p></td>
</tr>
<tr class="even">
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

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'extension de nom de fichier à supprimer. Exécutez Get-SPWOPIBinding pour obtenir la liste des extensions de noms de fichiers prises en charge par l'application WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'identificateur programmatique (ProgId) d'une application à supprimer. Exécutez Get-SPWOPIBinding pour obtenir la liste des ProgId pris en charge par l'application WOPI.</p></td>
</tr>
<tr class="even">
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

\--------------EXEMPLE 1-----------------

    New-SPWOPISuppressionSetting -Extension "XLSX" -Action "view"

    New-SPWOPISuppressionSetting -Extension "XLS" -Action "view"

Cet exemple montre comment désactiver la capacité d'un utilisateur à se servir de l'Office Web Apps pour afficher les classeurs Excel qui ont comme extensions de noms de fichiers « .xlsx » ou « .xls ».

## Voir aussi


[Get-SPWOPISuppressionSetting](get-spwopisuppressionsetting.md)  
[Remove-SPWOPISuppressionSetting](remove-spwopisuppressionsetting.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Office Web Apps avec SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

