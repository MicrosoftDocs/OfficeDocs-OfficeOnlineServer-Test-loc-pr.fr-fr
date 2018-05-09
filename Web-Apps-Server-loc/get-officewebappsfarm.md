---
title: Get-OfficeWebAppsFarm
TOCTitle: Get-OfficeWebAppsFarm
ms:assetid: 1f0704e1-a41d-40e6-a31b-08b1926ce811
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219434(v=office.15)
ms:contentKeyID: 49645191
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsFarm

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2013-12-18_

Renvoie des détails sur l'objet OfficeWebAppsFarm dont le serveur actuel est membre.

## Syntaxe

    Get-OfficeWebAppsFarm

## Description détaillée

La cmdlet **Get-OfficeWebAppsFarm** renvoie des détails sur l'objet OfficeWebAppsFarm dont le serveur actuel est membre. Cet objet représente un groupe de serveurs qui fonctionne comme une unité afin d'assurer l'édition et l'affichage web de documents Office. Aucun paramètre n'est utilisé avec la cmdlet **Get-OfficeWebAppsFarm**.

## Paramètres

## Types d'entrées

## Types de renvois

## Exemple

\------------------EXEMPLE 1---------------------

    Get-OfficeWebAppsFarm

Cet exemple montre comment renvoyer des détails sur l'objet OfficeWebAppsFarm.

\------------------EXEMPLE 2---------------------

    (Get-OfficeWebAppsFarm).Machines

Cet exemple montre comment renvoyer des détails sur les serveurs membres de la batterie Office Web Apps Server. Ces détails incluent l'état d'intégrité de chaque serveur et les rôles qu'ils tiennent.

## Voir aussi


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

