---
title: Get-OfficeWebAppsHost
TOCTitle: Get-OfficeWebAppsHost
ms:assetid: a9b766a7-a15c-4bbf-9750-31719406d65f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219446(v=office.15)
ms:contentKeyID: 49645225
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsHost

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2013-12-18_

Renvoie la liste des domaines hôtes figurant dans la liste verte d'une batterie de serveurs Office Web Apps Server.

## Syntaxe

    Get-OfficeWebAppsHost

## Description détaillée

La cmdlet **Get-OfficeWebAppsHost** permet de renvoyer la liste des domaines hôtes sur lesquels Office Web Apps Server autorise les demandes d'opérations sur des fichiers, telles que l'extraction de fichiers, l'extraction de métadonnées et les modifications de fichiers. Cette liste, également appelée liste verte, est une fonctionnalité de sécurité qui permet d'empêcher les hôtes indésirables de se connecter à une batterie Office Web Apps Server et de l'utiliser à son insu pour des opérations sur des fichiers.

Le caractère générique \* est supposé pour tous les domaines qui figurent dans la liste verte afin que les requêtes présentées à tous les sous-domaines soient également autorisées. Par exemple, si le domaine contoso.com figure dans la liste verte, alors Office Web Apps Server autorise également les requêtes présentées aux domaines corp.contoso.com et dev.contoso.com. En revanche, les requêtes présentées à d'autres domaines (tels que fabrikam.com) ne sont pas autorisées.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.Caution(Office.15).gif" title="Attention" alt="Attention" /><strong>Attention :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si aucun domaine ne figure dans la liste verte, Office Web Apps Server autorise les demandes de fichiers présentées aux hôtes de tous les domaines. Ne laissez pas cette liste vide si votre batterie Office Web Apps Server est accessible à partir d'Internet. Sinon, toute personne peut utiliser votre batterie Office Web Apps Server pour afficher et modifier du contenu.</td>
</tr>
</tbody>
</table>


## Paramètres

## Types d’entrées

## Types de retours

## Exemple

\------------------EXEMPLE 1---------------------

    Get-OfficeWebAppsHost

Cet exemple montre comment renvoyer les domaines hôtes figurant dans la liste verte.

## Voir aussi


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

