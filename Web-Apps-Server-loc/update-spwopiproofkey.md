---
title: Update-SPWOPIProofKey
TOCTitle: Update-SPWOPIProofKey
ms:assetid: fe7f3a87-082e-4a43-a5f3-7be41d8e91a3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219460(v=office.15)
ms:contentKeyID: 49645260
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Update-SPWOPIProofKey

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2015-03-09_

Met à jour la clé publique qui est utilisée pour connecter l'application WOPI sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

## Syntaxe

    Update-SPWOPIProofKey [-AssignmentCollection <SPAssignmentCollection>] [-ServerName <String>]

## Description détaillée

La cmdlet **Update-SPWOPIProofKey** met à jour la clé publique qui est utilisée pour connecter l'application WOPI (qui pourrait être un serveur exécutant l'Office Web Apps Server sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée. Vous souhaitez peut-être utiliser cette cmdlet si les clés se désynchronisent entre la batterie de serveurs SharePoint et l'application WOPI. En cas de désynchronisation de ces clés, les documents sont susceptibles de ne pas s'ouvrir dans le navigateur et les messages tels que « Signature de vérification non valide pour le fichier… » ou « Signature de vérification non valide pour le dossier... » sont identifiés dans les journaux ULS (Unified Logging System).

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

</div></td>
</tr>
<tr class="even">
<td><p><strong>ServerName</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'application WOPI à partir de laquelle obtenir la clé. Il peut s'agir d'un serveur qui exécute l'Office Web Apps Server. Si ce paramètre est manquant, les clés publiques pour toutes les applications WOPI qui sont connectées à la batterie de serveurs SharePoint actuelle, sont mises à jour.</p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\--------------EXEMPLE-----------------

    Update-SPWOPIProofKey -ServerName "Server.corp.Contoso.com"

Cet exemple montre comment obtenir la clé publique actuelle à partir de l'application WOPI (telle qu'un serveur exécutant Office Web Apps Server) et mettre à jour la clé qui est stockée dans la batterie de serveurs SharePoint.

## Voir aussi


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Office Web Apps avec SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

