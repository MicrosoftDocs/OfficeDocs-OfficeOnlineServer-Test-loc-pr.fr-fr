---
title: Planification d'Office Web Apps (utilisé avec SharePoint 2013)
TOCTitle: Planification d'Office Web Apps
ms:assetid: 3bd0a617-5f12-4a7e-bb75-b15c86c7e504
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Ff431682(v=office.15)
ms:contentKeyID: 49645201
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Planification d'Office Web Apps (utilisé avec SharePoint 2013)

 

_**Sapplique à :** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :** 2016-12-16_

**Résumé :** passez en revue les recommandations pour la planification d'Office Web Apps lorsque vous l'utilisez localement avec SharePoint 2013.

**Public concerné** : professionnels de l'informatique

Pour planifier la manière dont Office Web Apps est utilisé localement avec SharePoint 2013, vous devez vérifier la prise en charge des navigateurs, les conditions d'authentification SharePoint et les considérations relatives aux licences pour l'affichage et la modification de fichiers Office dans Office Web Apps. Ensuite, vous pouvez déterminer si vous souhaitez que SharePoint 2013 utilise le navigateur web ou une application cliente quand un utilisateur ouvre des fichiers Office à partir d'une bibliothèque de documents SharePoint 2013.

> [!IMPORTANT]
> Cet article s’inscrit dans la <a href="content-roadmap-for-office-web-apps-server.md">Feuille de route de contenu pour Office Web Apps</a>. Utilisez cette feuille de route comme point de départ pour accéder à des articles, téléchargements et vidéos qui vous aideront à déployer et à gérer Office Web Apps Server.<br />
<strong>Vous souhaitez obtenir de l’aide sur Office Web Apps sur les ordinateurs de bureau ou appareils mobiles ?</strong> Pour trouver les informations qui vous intéressent, recherchez « Office Web Apps » sur <a href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.


Contenu de cet article :

  - À propos de la planification d'Office Web Apps

  - Prise en charge des navigateurs pour Office Web Apps

  - Spécifications relatives à l'authentification SharePoint pour Office Web Apps

  - Licences Office Web Apps pour la modification de fichiers Office

  - Considérations relatives aux clients qui ont déployé Office Web Apps avec SharePoint 2010

  - Comportement d'ouverture par défaut pour les documents ouverts à partir des bibliothèques de documents SharePoint 2013

## À propos de la planification d'Office Web Apps

Les recommandations contenues dans cet article font référence à un sous-ensemble de la planification globale effectuée pendant le déploiement local de Office Web Apps Server dans votre organisation. Par exemple, la configuration matérielle, logicielle et de virtualisation requise, ainsi que la taille et la topologie des batteries, et la sécurité font partie intégrante de la planification d'Office Web Apps Server. Une fois que vous avez fait ces choix, vous pouvez planifier la configuration d'une fonctionnalité d'Office Web Apps spécifique de SharePoint 2013. Si vous ne connaissez pas Office Web Apps Server ou si vous n'avez pas eu connaissance des recommandations relatives à la configuration requise et la planification, consultez les rubriques [Vue d'ensemble d'Office Web Apps Server](office-web-apps-server-overview.md) et [Planification d'Office Web Apps Server](plan-office-web-apps-server.md).

## Prise en charge des navigateurs pour Office Web Apps

La prise en charge des navigateurs pour Office Web Apps est la même que pour SharePoint 2013. Pour plus d'informations, consultez l'article [Planifier la prise en charge du navigateur dans SharePoint 2013](https://technet.microsoft.com/fr-fr/library/cc263526\(v=office.15\)).

## Spécifications relatives à l'authentification SharePoint pour Office Web Apps

Office Web Apps ne peut être utilisé que par des applications web SharePoint 2013 qui utilisent une authentification basée sur les revendications. Le rendu et la modification dans Office Web Apps ne fonctionneront pas sur des applications web SharePoint 2013 qui utilisent un mode d'authentification classique. Si vous transférez des applications web SharePoint 2010 qui utilisent un mode d'authentification classique vers SharePoint 2013, vous devez les transférer vers une authentification basée sur les revendications pour leur permettre de fonctionner dans Office Web Apps. Pour plus d'informations, consultez la rubrique [Migrer de l’authentification en mode classique vers l’authentification basée sur les revendications dans SharePoint 2013](https://technet.microsoft.com/fr-fr/library/gg251985\(v=office.15\)).

## Licences Office Web Apps pour la modification de fichiers Office

Les entreprises clientes qui disposent d’une licence pour Office 2013 via un programme de licence en volume peuvent activer la modification Office Web Apps pour SharePoint 2013 localement. Cela permet d’activer les fonctionnalités de modification d’Office pour les utilisateurs, qu’ils se trouvent chez eux ou à d’autres emplacements où les clients Office peuvent ne pas être installés.

Pour obtenir des informations précises sur votre licence, consultez les Termes du contrat de licence logiciel Microsoft qui s’affichent lors de l’installation d’Office Web Apps Server. Pour plus d’informations sur l’octroi de licences dans SharePoint 2013, voir [Configurer la gestion des licences dans SharePoint Server 2013](https://technet.microsoft.com/fr-fr/library/jj219627\(v=office.15\)).

## Considérations relatives aux clients qui ont recours à la méthode de liaison de base de données pour la mise à niveau à partir de SharePoint 2010

Si vous avez installé Office Web Apps avec SharePoint 2010, Office Web Apps ne sera pas disponible après la mise à niveau vers SharePoint 2013. Vous devez déployer Office Web Apps Server et y connecter SharePoint 2013 après la mise à niveau des bases de données de contenu. Il n'est pas nécessaire d'attendre la mise à niveau des collections de sites car Office Web Apps Server prend en charge les collections de sites 2010 et 2013 dans SharePoint 2013. Pour plus d'informations sur la méthode de liaison de base de données, consultez la rubrique [Vue d’ensemble du processus de mise à niveau vers SharePoint 2013](https://technet.microsoft.com/fr-fr/library/cc262483\(v=office.15\)).

## Comportement d'ouverture par défaut pour les documents ouverts à partir des bibliothèques de documents SharePoint 2013

Vous pouvez configurer l'ouverture des fichiers Word, PowerPoint, Excel et OneNote dans une application cliente (si elle est installée) ou dans le navigateur. Par défaut, une fois que SharePoint 2013 est configuré pour utiliser Office Web Apps Server, les fichiers Office sont ouverts dans le navigateur. Le comportement par défaut peut être modifié de deux manières et ainsi autoriser les applications clientes à ouvrir les fichiers directement :

  - **Pour la batterie de serveurs SharePoint 2013** : vous pouvez définir le comportement d'ouverture par défaut en fonction du type de fichier pour la batterie de serveurs SharePoint 2013 à l'aide des cmdlets [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) et [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps)Windows PowerShell.

  - **Sur les collections de sites ou les bibliothèques de documents** : les administrateurs et les utilisateurs de collections de sites peuvent spécifier si les fichiers Office sont ouverts dans les applications clientes (si elles sont installées). Les utilisateurs peuvent modifier ce paramètre dans les propriétés des bibliothèques de documents et les administrateurs de collections de sites peuvent modifier ce paramètre dans Administration de la collection de sites ou à l'aide de la cmdlet Install-SPFeature pour installer la fonctionnalité OpenInClient. Pour plus d'informations, consultez la rubrique [Install-SPFeature](https://technet.microsoft.com/fr-fr/library/ff607825\(v=office.15\)).

## Voir aussi


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Fonctionnement de Office Web Apps sur site avec SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  


[Configuration de SharePoint 2013 Preview de manière à utiliser Office Web Apps Server Preview dans un environnement de test utilisant le protocole HTTP](configure-office-web-apps-for-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

