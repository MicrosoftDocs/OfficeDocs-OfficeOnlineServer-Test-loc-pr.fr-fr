---
title: Get-OfficeWebAppsMachine
TOCTitle: Get-OfficeWebAppsMachine
ms:assetid: 02fadf5e-0382-4e73-8d07-e67d088b1a02
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219432(v=office.15)
ms:contentKeyID: 49645187
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsMachine

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2013-12-18_

Renvoie des détails sur le serveur actuel qui se trouve dans une batterie de serveurs Office Web Apps Server.

## Syntaxe

    Get-OfficeWebAppsMachine

## Description détaillée

La cmdlet **Get-OfficeWebAppsMachine** renvoie des détails sur le serveur actuel qui se trouve dans une batterie de serveurs Office Web Apps Server. Ces détails incluent les rôles et l'état d'intégrité du serveur actuel, ainsi que le nom du serveur maître de la batterie.

## Paramètres

## Types d'entrées

## Types de renvois

## Exemple

\------------------EXEMPLE 1---------------------

    Get-OfficeWebAppsMachine

Cet exemple montre comment renvoyer des détails sur le serveur actuel qui se trouve dans une batterie de serveurs Office Web Apps Server.

\------------------EXEMPLE 2---------------------

    (Get-OfficeWebAppsFarm).Machines

Cet exemple montre comment renvoyer des détails sur tous les serveurs qui figurent dans une batterie de serveurs Office Web Apps Server.

## Voir aussi


[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

