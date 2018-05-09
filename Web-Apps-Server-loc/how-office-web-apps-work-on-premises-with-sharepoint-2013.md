---
title: Fonctionnement de Office Web Apps sur site avec SharePoint 2013
TOCTitle: Office Web Apps sur site avec SharePoint 2013
ms:assetid: 8480064e-14a4-4b46-ad6b-0c836b192af2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Ff431685(v=office.15)
ms:contentKeyID: 49645215
ms.date: 01/28/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Fonctionnement de Office Web Apps sur site avec SharePoint 2013

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2016-12-16_

**Résumé** : fournit des informations sur Office Web Apps, Office Web Apps Server et leur fonctionnement en local avec SharePoint 2013.

**Public concerné** : professionnels de l’informatique

En cas d’utilisation avec SharePoint Server 2013, Office Web Apps Server fournit des versions mises à jour de Word Web App, Excel Web App, PowerPoint Web App et OneNote Web App. Les utilisateurs peuvent afficher et, dans certains cas, modifier des documents Office dans des bibliothèques SharePoint à l’aide d’un navigateur web pris en charge sur des ordinateurs et sur de nombreux périphériques mobiles, tels que des téléphones Windows Phone, des iPhone, des iPad, des tablettes Windows 8 et des périphériques Android.


**Figure : Capacités d’affichage et de modification d’Office Web Apps sur différents types d’appareils.**

![Graphique résumant les capacités d’affichage et de modification d’Office Web Apps sur différents types d’appareils. Il met en évidence ceux optimisés pour les écrans tactiles.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Graphique résumant les capacités d’affichage et de modification d’Office Web Apps sur différents types d’appareils. Il met en évidence ceux optimisés pour les écrans tactiles.")

## Office Web Apps Server est maintenant installé comme serveur autonome

Office Web Apps n’est pas installé sur les serveurs qui exécutent SharePoint 2013. En réalité, vous déployez un ou plusieurs serveurs physiques ou virtuels exécutant Office Web Apps Server. Vous configurez ensuite la batterie de serveurs SharePoint 2013 pour qu’elle utilise la batterie de serveurs Office Web Apps Server et offre la fonctionnalité Office Web Apps aux utilisateurs qui créent ou ouvrent des fichiers Office dans des bibliothèques SharePoint. Pour plus d’informations, voir [Vue d'ensemble d'Office Web Apps Server](office-web-apps-server-overview.md).

## Options pour les licences d’Office Web Apps en cas d’utilisation avec SharePoint 2013

Les licences Office Web Apps offrent deux options :

  - **Affichage seul** : par défaut, Office Web Apps est disponible en mode Affichage seul. La fonctionnalité Affichage seul est gratuite.

  - **Modifier et afficher**. Vous devrez acheter une licence d’accès en modification pour utiliser les fonctions de modification d’Office Web Apps avec SharePoint 2013. Vous activez la modification à la création de la batterie de serveurs Office Web Apps Server.

Si votre organisation gère les licences pour Office 2013 via un programme de licence en volume, vous pouvez activer la modification Office Web Apps pour SharePoint 2013 en local. Cela permet d’activer les fonctionnalités de modification d’Office pour les utilisateurs, qu’ils se trouvent chez eux ou à d’autres emplacements où les clients Office ne peuvent pas être installés. Des licences de modification pour Office Web Apps ne sont pas disponibles pour un achat séparé.

Pour obtenir des informations précises sur votre licence, consultez les Termes du contrat de licence logiciel Microsoft qui s’affichent lors de l’installation d’Office Web Apps Server.

SharePoint 2013 permet l’application d’une nouvelle licence qui fonctionne avec Office Web Apps. Si vous activez les licences SharePoint et que vous activez ensuite la modification pour Office Web Apps, seuls les utilisateurs qui disposent de la licence appropriée peuvent réellement modifier des fichiers Office dans un navigateur. Si aucune licence d’accès en modification Office Web Apps n’est appliquée pour les utilisateurs, seul l’affichage est pris en charge.

Pour plus d’informations sur l’utilisation des licences dans SharePoint 2013, voir [Configurer la gestion des licences dans SharePoint Server 2013](https://technet.microsoft.com/fr-fr/library/jj219627\(v=office.15\)). Le paramètre EditingEnabled qui autorise la modification est décrit dans [New-OfficeWebAppsFarm](new-officewebappsfarm.md) et [Set-OfficeWebAppsFarm](set-officewebappsfarm.md).

Les fichiers transmis à l’aide de la fonctionnalité de partage par un lien disponible dans SharePoint 2013 peuvent être modifiés dans Office Web Apps même si aucune licence de modification n’est présente et lorsque la modification est désactivée pour la batterie Office Web Apps Server.

## Utiliser des visionneuses Office Mobile pour accéder aux fichiers sur des sites SharePoint

Office Web Apps Server fournit des visionneuses Office Mobile pour mettre Office Web Apps à la disposition des utilisateurs mobiles qui accèdent aux sites SharePoint Server. Les visionneuses Office Mobile sont activées par défaut, mais elles peuvent être désactivées par l’administrateur du site SharePoint Server. Lorsqu’elles sont activées, les utilisateurs peuvent accéder au site SharePoint Server à l’aide du navigateur sur leur périphérique mobile et appuyer sur le document à ouvrir dans la bibliothèque SharePoint Server. Le document s’ouvre alors dans le navigateur mobile.

Vous pouvez obtenir plus d’informations concernant les bibliothèques SharePoint sur les périphériques mobiles dans [What's new for mobile devices in SharePoint 2013](https://technet.microsoft.com/fr-fr/library/fp161352\(v=office.15\)) et [Vue d’ensemble des appareils mobiles et de SharePoint Server 2013](https://technet.microsoft.com/fr-fr/library/fp161351\(v=office.15\)). Les utilisateurs peuvent en savoir plus sur l’utilisation des visionneuses Office Mobile sur leur périphérique mobile dans [Utiliser Office Web Apps sur un téléphone Android, iPhone ou Windows](http://go.microsoft.com/fwlink/p/?linkid=271045). Si vous décidez de désactiver les visionneuses Office Mobile sur SharePoint 2013, utilisez la cmdlet [Remove-SPWOPIBinding](remove-spwopibinding.md).

## Différences entre Excel Web App et Excel Services dans SharePoint

Excel Web App et Excel Services dans SharePoint ont beaucoup en commun, mais ne sont pas identiques. Excel Services est disponible uniquement avec l’édition Enterprise de SharePoint Server 2013. Excel Web App est disponible dans SharePoint Server 2013 et SharePoint Foundation 2013. Les deux applications vous permettent d’afficher des classeurs dans une fenêtre de navigateur, mais aussi d’interagir avec des données et de les explorer.

Il existe toutefois certaines différences entre Excel Web App et Excel Services dans SharePoint. Excel Services prend en charge les connexions de données externes et les modèles de données, et permet d’interagir avec des éléments qui utilisent les modèles de données (tels que des rapports de graphique croisé dynamique, des rapports de tableau croisé dynamique et des contrôles de chronologie). Excel Services offre une fonction d’aide à la décision plus développée que Excel Web App mais Excel Services ne permet pas aux utilisateurs de créer ou de modifier des classeurs dans une fenêtre de navigateur.

Pour plus de détails sur les différences entre Excel Web App et Excel Services, voir [Vue d’ensemble d’Excel Services dans SharePoint Server 2013](https://technet.microsoft.com/fr-fr/library/ee424405\(v=office.15\)) et [Comparaison d’Excel Services dans SharePoint à Excel Web App](http://go.microsoft.com/fwlink/p/?linkid=255460).

Si votre organisation décide d’utiliser Excel Services à la place de Excel Web App pour afficher les classeurs dans le navigateur, vous pouvez utiliser la cmdlet Windows PowerShell **New-SPWOPISuppressionSettings** pour désactiver Excel Web App pour les classeurs Excel. Pour plus d’informations, consultez la rubrique [New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md).

## Voir aussi


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Planification d'Office Web Apps (utilisé avec SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
  

[](plan-office-web-apps-used-with-sharepoint-2013.md)

