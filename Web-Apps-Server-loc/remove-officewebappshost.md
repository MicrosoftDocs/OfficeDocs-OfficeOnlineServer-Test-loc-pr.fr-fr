---
title: Remove-OfficeWebAppsHost
TOCTitle: Remove-OfficeWebAppsHost
ms:assetid: d0f7b5c2-da0f-421a-8478-c39b247c3ac5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219453(v=office.15)
ms:contentKeyID: 49645242
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsHost

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Supprime un domaine hôte de la liste verte d'une batterie de serveurs Office Web Apps Server.

## Syntaxe

    Remove-OfficeWebAppsHost -Domain <String>

## Description détaillée

La cmdlet **Remove-OfficeWebAppsHost** supprime le domaine hôte spécifié de la liste verte. La liste verte contient les domaines hôtes sur lesquels Office Web Apps Server autorise les demandes d'opérations sur des fichiers.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.Caution(Office.15).gif" title="Attention" alt="Attention" /><strong>Attention :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si aucun domaine ne figure dans la liste verte, Office Web Apps Server autorise les demandes de fichiers présentées aux hôtes de tous les domaines. Ne laissez pas cette liste vide si votre batterie Office Web Apps Server est accessible depuis Internet. Sinon, toute personne peut utiliser votre batterie Office Web Apps Server pour afficher et modifier du contenu.</td>
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
<th>Statut</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Domain</strong></p></td>
<td><p>Obligatoire</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le domaine hôte à supprimer de la liste verte.</p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\------------------EXEMPLE 1---------------------

    Remove-OfficeWebAppsHost -domain "contoso.com"

Cet exemple montre comment supprimer le domaine contoso.com de la liste verte.

## Voir aussi


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Get-OfficeWebAppsHost](get-officewebappshost.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

