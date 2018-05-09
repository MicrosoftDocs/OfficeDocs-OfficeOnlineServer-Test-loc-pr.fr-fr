---
title: New-OfficeWebAppsMachine
TOCTitle: New-OfficeWebAppsMachine
ms:assetid: b0385c4e-61fc-4607-a48c-64d8f4e80651
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219449(v=office.15)
ms:contentKeyID: 49645234
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsMachine

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Ajoute le serveur actuel à une batterie de serveurs Office Web Apps Server existante.

## Syntaxe

    New-OfficeWebAppsMachine [-MachineToJoin] <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **New-OfficeWebAppsMachine** ajoute le serveur actuel à une batterie de serveurs Office Web Apps Server existante et définit éventuellement un ou plusieurs rôles sur le nouveau serveur.

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
<td><p><strong>MachineToJoin</strong></p></td>
<td><p>Requis</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le nom d'un serveur déjà membre de la batterie de serveurs Office Web Apps Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppose que la réponse à une invite utilisateur, quelle qu'elle soit, est Oui.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rôles</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String[]</p></td>
<td><p>Spécifie un ou plusieurs rôles serveur, séparés par des virgules, à assigner au nouveau serveur. Si aucun rôle n'est spécifié, le serveur reçoit tous les rôles.</p>
<p>Les types de rôles sont les suivants :</p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>En guise de meilleure pratique, il est recommandé que tous les serveurs d'une batterie de serveurs Office Web Apps Server exécutent tous les rôles. L'affectation de rôles ne s'avère pas utile tant que la batterie de serveurs Office Web Apps Server ne contient pas une cinquantaine de serveurs.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
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

    New-OfficeWebAppsMachine -MachineToJoin server1.contoso.com

Cet exemple montre comment ajouter le serveur actuel à la batterie de serveurs Office Web Apps Server qui est en cours d'exécution sur le serveur nommé server1.contoso.com.

## Voir aussi


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

