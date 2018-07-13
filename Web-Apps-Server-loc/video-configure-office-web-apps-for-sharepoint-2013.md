---
title: 'Vidéo : Configurer Office Web Apps pour SharePoint 2013'
TOCTitle: 'Vidéo : Configurer Office Web Apps pour SharePoint 2013'
ms:assetid: 0c02633f-3839-448b-ae83-24f24c254179
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn455088(v=office.15)
ms:contentKeyID: 59152166
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Vidéo : Configurer Office Web Apps pour SharePoint 2013

 

_**Sapplique à :** Office Web Apps, Office Web Apps Server, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :** 2016-12-16_

**Résumé** : vous guide tout au long des neuf étapes principales à suivre pour configurer une batterie de serveurs Office Web Apps Server afin que celle-ci fonctionne avec SharePoint 2013.

La configuration d’Office Web Apps pour SharePoint 2013 est un processus relativement simple. Cette vidéo vous montre comment installer Office Web Apps Server et configurer SharePoint 2013 afin d’utiliser Office Web Apps Server dans un environnement de test.


**Regardez la vidéo « Configurer Office Web Apps pour SharePoint 2013 ».**

> [!VIDEO https://www.microsoft.com/fr-fr/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

Cette vidéo porte sur les procédures réalisées sur deux serveurs : le serveur qui exécute Office Web Apps Server et celui qui exécute SharePoint 2013. Il doit s’agir de serveurs distincts, comme décrit dans [Configuration logicielle et matérielle requise pour Office Web Apps Server](plan-office-web-apps-server.md).

**Sur le serveur qui exécute Office Web Apps Server, la vidéo montre comment effectuer les actions suivantes :**

NCO 1. Ouvrir l’invite de commandes Windows PowerShell et installer les rôles et services requis pour Office Web Apps Server. Voir [Préparer des serveurs pour l'exécution d'Office Web Apps Server](deploy-office-web-apps-server.md). Ceci est nécessaire, car Office Web Apps Server ne sera pas installé si les rôles et services requis sont manquants.  
2\. Installer le logiciel Office Web Apps Server à partir du [Centre de gestion des licences en volume](http://go.microsoft.com/fwlink/p/?linkid=256561). Pour télécharger Office Web Apps Server, vous devez disposer d’une licence dans le cadre d’un contrat de licence en volume pour Office Professionnel Plus 2013, Office Standard 2013 ou Office pour Mac 2011. Le téléchargement est disponible sous ces produits Office sur le portail du Centre de gestion des licences en volume.  
3\. Créer la batterie de serveurs Office Web Apps Server à l’aide de [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).  
4\. Vérifier que la batterie de serveurs Office Web Apps Server a été créée en ouvrant une fenêtre de navigateur et en accédant à http://*ServerName*/hosting/discovery.

**Sur le serveur qui exécute SharePoint 2013, la vidéo montre comment effectuer les actions suivantes :**

5\. Ouvrir SharePoint 2013 Management Shell.  
6\. Créer la liaison entre Office Web Apps Server et SharePoint 2013 à l’aide de [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps). Ceci configure la communication entre le serveur qui exécute SharePoint 2013 et celui qui exécute Office Web Apps Server.  
7\. Afficher la zone WOPI de SharePoint 2013 à l’aide de [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps). Cette étape met en évidence le fait que les deux serveurs utilisent des zones WOPI différentes : SharePoint 2013 utilise la zone internal-https, tandis que Office Web Apps Server utilise la zone internal-http. La zone doit correspondre pour qu’Office Web Apps fonctionne correctement.  
8\. Modifier la zone WOPI de SharePoint 2013 à l’aide de [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps), afin de changer la zone WOPI en internal-http.  
9\. Vérifier qu’Office Web Apps fonctionne en ouvrant un document Office dans une bibliothèque de documents SharePoint 2013.

Pour plus de détails sur chacune de ces étapes, consultez les sections suivantes dans les articles [Déployer Office Web Apps Server](deploy-office-web-apps-server.md) et [Configurer Office Web Apps pour SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

  - [Préparer des serveurs pour l'exécution d'Office Web Apps Server](deploy-office-web-apps-server.md)

  - [Déployer une batterie Office Web Apps Server à serveur unique dans un environnement de test](deploy-office-web-apps-server.md)

  - [Préparer la configuration de SharePoint 2013 pour l'utilisation d'Office Web Apps Server](configure-office-web-apps-for-sharepoint-2013.md)

  - [In a test environment that uses HTTP](configure-office-web-apps-for-sharepoint-2013.md)

## Voir aussi


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Planification d'Office Web Apps (utilisé avec SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
[Fonctionnement de Office Web Apps sur site avec SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

