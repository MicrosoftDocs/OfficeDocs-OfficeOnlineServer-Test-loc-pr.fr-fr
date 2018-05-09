---
title: Repair-OfficeWebAppsFarm
TOCTitle: Repair-OfficeWebAppsFarm
ms:assetid: 083d8e25-ce82-4884-9bbc-06375185011c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219433(v=office.15)
ms:contentKeyID: 49645189
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Repair-OfficeWebAppsFarm

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Supprime tous les serveurs marqués comme défectueux d'une batterie de serveurs Office Web Apps Server.

## Syntaxe

    Repair-OfficeWebAppsFarm [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **Repair-OfficeWebAppsFarm** supprime tous les serveurs marqués comme défectueux d'une batterie de serveurs Office Web Apps Server. Elle met à jour la topologie de batterie de serveurs mais ne nettoie pas les services et applications Web sur les serveurs supprimés. C'est pourquoi nous vous recommandons de vous efforcer d'exécuter la cmdlet **Remove-OfficeWebAppsMachine** depuis les serveurs défectueux afin qu'ils soient proprement supprimés de la batterie. Utilisez la cmdlet **Repair-OfficeWebAppsFarm** uniquement en cas d'échec des serveurs défectueux et lorsque vous ne pouvez pas exécuter la cmdlet **Remove-OfficeWebAppsMachine** directement sur eux.

S'il existe plusieurs serveurs défectueux, vous êtes invité à confirmer la suppression de chacun d'eux. En l'absence de serveurs défectueux, cette cmdlet n'effectue aucune action.

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
<th>Requis</th>
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
<td><p><strong>Force</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppose que la réponse à une invite utilisateur, quelle qu'elle soit, est OUI.</p></td>
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

## Types de renvois

## Exemple

\------------------EXEMPLE 1---------------------

    (Get-OfficeWebAppsFarm).Machines

Cet exemple montre comment afficher l'état d'intégrité de tous les serveurs inclus dans la batterie Office Web Apps Server.

\------------------EXEMPLE 2---------------------

    Repair-OfficeWebAppsFarm

Cet exemple montre comment supprimer tous les serveurs défectueux de la batterie Office Web Apps Server.

## Voir aussi


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

