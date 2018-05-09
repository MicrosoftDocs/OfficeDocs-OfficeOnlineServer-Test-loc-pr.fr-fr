---
title: Get-SPWOPIZone
TOCTitle: Get-SPWOPIZone
ms:assetid: 5a37e106-272c-43e9-ae09-20888b296af0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219439(v=office.15)
ms:contentKeyID: 49645207
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPIZone

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2015-03-09_

Renvoie la zone qui est configurée sur la batterie de serveurs SharePoint actuelle à utiliser par l'application WOPI.

## Syntaxe

    Get-SPWOPIZone [-AssignmentCollection <SPAssignmentCollection>]

## Description détaillée

**Get-SPWOPIZone** renvoie la zone qui est configurée sur la batterie de serveurs SharePoint actuelle à utiliser par l'application WOPI (tel qu'un serveur exécutant l'Office Web Apps Server).

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
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\--------------EXEMPLE-----------------

    Get-SPWOPIZone

Cet exemple montre comment renvoyer la zone qui est configurée pour être utilisée par l'application WOPI (tel qu'un serveur exécutant l'Office Web Apps Server). Les valeurs renvoyées peuvent être « internal-http », « internal-https », « external-http » ou « external-https ».

## Voir aussi


[Set-SPWOPIZone](set-spwopizone.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Office Web Apps avec SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

