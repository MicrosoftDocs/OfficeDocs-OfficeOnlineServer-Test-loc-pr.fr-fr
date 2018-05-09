---
title: Remove-OfficeWebAppsMachine
TOCTitle: Remove-OfficeWebAppsMachine
ms:assetid: 5ad806f2-67c6-41ed-a708-69db800f492a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219440(v=office.15)
ms:contentKeyID: 49645208
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsMachine

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Supprime le serveur actuel de la batterie Office Web Apps Server.

## Syntaxe

    Remove-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **Remove-OfficeWebAppsMachine** supprime le serveur actuel de la batterie Office Web Apps Server. Dans le cadre de ce processus, la cmdlet supprime les applications web et arrête les services associés à Office Web Apps Server. Si vous ne pouvez pas exécuter la cmdlet **Remove-OfficeWebAppsMachine** depuis le serveur à supprimer, utilisez la cmdlet **Repair-OfficeWebAppsFarm** depuis un autre serveur de la batterie Office Web Apps.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si le serveur local est désigné serveur maître dans la batterie Office Web Apps Server, vous ne pouvez pas le supprimer de la batterie tant que vous n'avez pas attribué un autre serveur en tant que maître à la cmdlet <strong>Set-OfficeWebAppsMachine</strong> ou tant que vous n'avez pas supprimé tous les autres serveurs de la batterie.</td>
</tr>
</tbody>
</table>


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
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Affiche un message qui explique l’effet de la commande au lieu de l’exécuter. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\------------------EXEMPLE 1---------------------

    Remove-OfficeWebAppsMachine

Cet exemple montre comment supprimer le serveur actuel de la batterie Office Web Apps Server.

## Voir aussi


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

