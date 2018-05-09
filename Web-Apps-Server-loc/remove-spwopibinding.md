---
title: Remove-SPWOPIBinding
TOCTitle: Remove-SPWOPIBinding
ms:assetid: 52855c21-ee2c-497a-b308-bf5eeabe4bbe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219438(v=office.15)
ms:contentKeyID: 49645204
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPIBinding

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2015-03-09_

Supprime les liaisons des applications, des extensions de noms de fichiers et leurs actions associées sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

## Syntaxe

    Remove-SPWOPIBinding [[-Identity] <SPWopiBindingPipeBind>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WhatIf [<SwitchParameter>]] [-WOPIZone <String>]

    Remove-SPWOPIBinding [-All <SwitchParameter>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **Remove-SPWOPIBinding** supprime les liaisons des applications, des extensions de noms de fichiers et leurs actions associées sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée. Une fois que vous avez exécuté cette cmdlet, vous pouvez utiliser **New-SPWOPIBinding** pour recréer les liaisons en fonction des besoins. Si vous supprimez toutes les liaisons pour une application, les utilisateurs ne peuvent pas utiliser Office Web Apps ni le partage SharePoint via une fonctionnalité de lien pour cette application. Si vous supprimez toutes les liaisons sur la batterie de serveurs SharePoint sur laquelle cette cmdlet est exécutée, les utilisateurs ne peuvent pas utiliser Office Web Apps ni le partage SharePoint via une fonctionnalité de lien pour toute application de la bibliothèque SharePoint.

Vous pouvez cesser d'utiliser Office Web Apps pour les clics par défaut et conserver les informations de découverte relatives aux liaisons ainsi que la capacité pour les utilisateurs à se servir du partage SharePoint via une fonctionnalité de lien pour envoyer un lien vers un document et permettre au destinataire d'utiliser Office Web Apps pour ce type de document. Vous utilisez à la place la cmdlet **New-SPWOPISuppression**.

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
<td><p><strong>Identity</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Spécifie la liaison.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'action pour laquelle les liaisons sont à supprimer. Par exemple, « afficher », « modifier » et « afficher en mode incorporé ». Pour obtenir une liste des actions, exécutez <strong>Get-SPWOPIBinding</strong>. De manière plus générale, vous n'aurez pas recours à ce paramètre. Si vous spécifiez certaines actions mais pas d'autres, certaines fonctionnalités SharePoint pourraient ne pas fonctionner.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Supprime toutes les liaisons.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'application pour laquelle les liaisons sont à supprimer. Les applications possibles sont les suivantes : « Word », « Excel », « PowerPoint » ou « OneNote ». Exécutez <strong>Get-SPWOPIBinding</strong> pour obtenir la liste des applications.</p></td>
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

</div></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie les extensions de noms de fichiers pour lesquelles les liaisons sont à supprimer. Exécutez <strong>Get-SPWOPIBinding</strong> pour obtenir la liste des extensions de noms de fichiers.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'identificateur programmatique (ProgID) de l'application pour laquelle les liaisons sont à supprimer. Exécutez <strong>Get-SPWOPIBinding</strong> pour obtenir la liste des ProgID. Vous pouvez aussi réserver ce paramètre à la tâche des liaisons OneNote.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le nom de l'application WOPI (par exemple Office Web Apps Server) pour laquelle les liaisons sont à supprimer.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Affiche un message qui explique l’effet de la commande au lieu de l’exécuter. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie la zone pour laquelle les liaisons sont à supprimer.</p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\--------------EXEMPLE 1-----------------

    Remove-SPWOPIBinding -Application "Excel"

Cet exemple montre comment supprimer toutes les liaisons d'Excel sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

\--------------EXEMPLE 2-----------------

    Remove-SPWOPIBinding -All:$true

Cet exemple montre comment supprimer toutes les liaisons sur la batterie de serveurs SharePoint sur laquelle cette cmdlet est exécutée.

\--------------EXEMPLE 3-----------------

    Get-SPWOPIBinding -Action "MobileView" | Remove-SPWOPIBinding

Cet exemple montre comment supprimer toutes les liaisons d'Office Mobile Web Apps sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

## Voir aussi


[New-SPWOPIBinding](new-spwopibinding.md)  
[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Office Web Apps avec SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

