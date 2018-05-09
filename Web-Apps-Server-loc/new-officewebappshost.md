---
title: New-OfficeWebAppsHost
TOCTitle: New-OfficeWebAppsHost
ms:assetid: f1d523ab-45c6-4e3c-b274-22c0d229a6a0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219459(v=office.15)
ms:contentKeyID: 49645257
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsHost

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Ajoute un domaine hôte à la liste verte d'une batterie Office Web Apps Server.

## Syntaxe

    New-OfficeWebAppsHost -Domain <String>

## Description détaillée

La cmdlet **New-OfficeWebAppsHost** ajoute un domaine hôte à la liste des domaines hôtes sur lesquels Office Web Apps Server autorise les demandes d’opérations sur des fichiers, telles que l’extraction de fichiers, l’extraction de métadonnées et les modifications de fichiers. Cette liste, également appelée liste verte, est une fonctionnalité de sécurité qui permet d’empêcher les hôtes indésirables de se connecter à une batterie Office Web Apps Server et de l’utiliser à son insu pour des opérations sur des fichiers.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.tip(Office.15).gif" title="Conseil" alt="Conseil" /><strong>Conseil :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous pouvez indiquer n’importe quel type de domaine, notamment les suivants : noms de domaine publics, de pool, de batterie et Active Directory. Assurez-vous simplement que le domaine auquel vous accordez l’accès répond aux exigences de sécurité.</td>
</tr>
</tbody>
</table>


Le caractère générique \* est supposé pour tous les domaines ajoutés à la liste verte afin que les requêtes présentées à tous les sous-domaines soient également autorisées. Par exemple, si vous ajoutez le domaine contoso.com à la liste verte, Office Web Apps Server autorise également les requêtes présentées aux domaines corp.contoso.com et dev.contoso.com. En revanche, les requêtes présentées à d'autres domaines (tels que fabrikam.com) ne sont pas autorisées.

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
<td><p>Spécifie le domaine à ajouter à la liste verte. Ne spécifiez pas d'astérisque et ne débutez pas par un point.</p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\------------------EXEMPLE 1---------------------

    New-OfficeWebAppsHost -domain "contoso.com"

Cet exemple montre comment ajouter le domaine contoso.com à la liste verte.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous ne pouvez pas ajouter plusieurs domaines hôtes dans la liste verte au même moment. Vous devez exécuter la cmdlet New-OfficeWebAppsHost pour chaque domaine hôte que vous voulez ajouter à la liste verte.</td>
</tr>
</tbody>
</table>


## Voir aussi


[Get-OfficeWebAppsHost](get-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

