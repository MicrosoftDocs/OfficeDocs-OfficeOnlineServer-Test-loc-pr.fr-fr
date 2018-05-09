---
title: Vue d'ensemble d'Office Web Apps Server
TOCTitle: 'Vue d’ensemble : Office Web Apps Server'
ms:assetid: 4b199a88-387f-4121-820d-7af580e2a3e8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219437(v=office.15)
ms:contentKeyID: 49645203
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Vue d'ensemble d'Office Web Apps Server

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2017-05-26_

**Résumé :** découvrez Office Web Apps Server et sa fonctionnalité Office dans un navigateur pour les hôtes pris en charge.

**Public concerné** : professionnels de l'informatique

Office Web Apps Server est un nouveau produit du serveur Office qui offre des versions de Word, PowerPoint, Excel et OneNote basées sur le navigateur. Une seule batterie Office Online Server peut prendre en charge des utilisateurs qui accèdent aux fichiers Office via SharePoint 2013, Lync Server 2013, des dossiers partagés et des sites web. Le nouveau modèle de déploiement autonome signifie que vous pouvez gérer des mises à jour de votre batterie Office Online Server indépendamment des autres produits du serveur Office déployés dans votre organisation.

<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cet article s’inscrit dans la <a href="content-roadmap-for-office-web-apps-server.md">Feuille de route de contenu pour Office Web Apps</a>. Utilisez cette feuille de route comme point de départ pour accéder à des articles, téléchargements et vidéos qui vous aideront à déployer et gérer Office Web Apps Server.<br />
<strong>Vous souhaitez obtenir de l’aide sur Office Web Apps sur les ordinateurs de bureau ou appareils mobiles ?</strong> Pour trouver les informations qui vous intéressent, recherchez « Office Web Apps » sur <a href="https://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.</td>
</tr>
</tbody>
</table>


Contenu de cet article :

  - À propos d'Office Web Apps Server

  - Utilisation d'Office Web Apps Server par SharePoint 2013 pour afficher et modifier des documents Office

  - Utilisation d'Office Web Apps Server par Lync Server 2013 pour afficher des diffusions PowerPoint

  - Utilisation d'Office Web Apps Server pour afficher des fichiers Office dans des dossiers partagés et des sites web à l'aide des visionneuses en ligne

## À propos d'Office Web Apps Server

Office Web Apps Server est un produit du serveur Office qui permet d’afficher et de modifier des fichiers Office dans un navigateur. Office Web Apps Server utilise des produits et des services qui prennent en charge le protocole WOPI. Ces produits, qui sont aussi des hôtes, comprennent SharePoint 2013 et Lync Server 2013. Une batterie Office Online Server peut offrir des services Office à plusieurs hôtes locaux. De plus, vous pouvez monter en charge votre batterie en passant d’un serveur unique à plusieurs serveurs à mesure que les besoins de votre organisation évoluent. Même si Office Web Apps Server nécessite des serveurs dédiés qui n’exécutent aucune autre application serveur, vous pouvez installer à la place Office Web Apps Server sur des instances de machine virtuelle.

Il est désormais plus facile de déployer et de gérer Office Web Apps au sein de votre organisation en tant que produit autonome. Si vous déployez SharePoint 2013, par exemple, vous n’avez plus à optimiser l’infrastructure SharePoint pour prendre en charge Office Web Applications, qui, dans les versions précédentes, était étroitement intégré à SharePoint Server 2010. Vous pouvez également appliquer des mises à jour à la batterie Office Online Server séparément et à une fréquence différente des mises à jour de SharePoint ou Lync Server. Une batterie Office Online Server autonome implique aussi que les utilisateurs peuvent afficher ou modifier des fichiers Office stockés en dehors de SharePoint Server, comme dans des dossiers partagés ou d’autres sites web. Cette fonctionnalité est offerte par les visionneuses en ligne.

L'illustration suivante montre les différences existant entre le modèle de déploiement précédent d'Office Web Apps et le nouveau modèle de déploiement autonome pour Office Web Apps.

**Différences entre les modèles de déploiement d'Office Web Apps**

![Montre la différence entre le modèle de déploiement précédent et le nouveau modèle de déploiement autonome pour Office Web Apps Server](images/JJ219437.f16dd9d1-c9b7-4c8b-a8de-f1f82c0ee1e2(Office.15).gif "Montre la différence entre le modèle de déploiement précédent et le nouveau modèle de déploiement autonome pour Office Web Apps Server")

## Utilisation d'Office Web Apps Server par SharePoint 2013 pour afficher et modifier des documents Office

Lorsqu'il est utilisé avec SharePoint Server 2013, Office Web Apps Server procure des versions mises à jour de Word Web App, Excel Web App, PowerPoint Web App et OneNote Web App. Les utilisateurs peuvent afficher et, dans certains, cas modifier des documents Office dans des bibliothèques SharePoint à l'aide d'un navigateur web pris en charge sur des ordinateurs et sur bon nombre d'appareils mobiles, tels que Windows Phones, iPhones, iPads et les tablettes Windows 8. Parmi les nombreuses nouvelles fonctionnalités présentes dans Office Web Apps, les capacités améliorées de prise en charge tactile et de modification permettent aux utilisateurs d'iPads et de tablettes Windows 8 de pouvoir modifier et afficher des documents Office directement sur leurs appareils.

L'illustration suivante résume les capacités d'affichage et de modification d'Office Web Apps sur différents types d'appareils.

**Capacité d'affichage et de modification d'Office Web Apps**

![Graphique résumant les capacités d’affichage et de modification d’Office Web Apps sur différents types d’appareils. Il met en évidence ceux optimisés pour les écrans tactiles.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Graphique résumant les capacités d’affichage et de modification d’Office Web Apps sur différents types d’appareils. Il met en évidence ceux optimisés pour les écrans tactiles.")

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Le service de diffusion PowerPoint a été supprimé de SharePoint 2013. Il est accessible par le biais de OneDrive et de Lync Server 2013.</td>
</tr>
</tbody>
</table>


Pour plus d'informations sur les nouveautés de Office Web Apps, consultez la rubrique [Fonctionnement de Office Web Apps sur site avec SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md).

## Utilisation d'Office Web Apps Server par Lync Server 2013 pour afficher des diffusions PowerPoint

Dans Lync Server 2010, les présentations PowerPoint sont affichées de deux manières. Pour les utilisateurs de Lync 2010, les présentations PowerPoint sont affichées au format PowerPoint 97-2003 dans une copie incorporée de la visionneuse PowerPoint. Pour les utilisateurs de Lync Web App, les présentations PowerPoint sont converties en fichiers HTML dynamiques puis affichées dans une combinaison de fichiers DHTML personnalisés et de Silverlight. Bien que cette approche s'avère généralement efficace, elle comporte certaines limitations :

  - La visionneuse PowerPoint incorporée (qui fournissait un affichage optimal) n'est disponible que sur la plateforme Windows.

  - Bon nombre d'appareils mobiles (notamment certains des téléphones mobiles les plus populaires) ne prennent pas en charge Silverlight.
    
    Ni la visionneuse PowerPoint, ni l'approche DHTML/Silverlight ne prennent en charge toutes les fonctionnalités (notamment la transition des diapositives et la vidéo incorporée) que l'on trouve dans les dernières éditions de PowerPoint.

Pour contourner ces problèmes et pour améliorer l'expérience globale de présentation ou consultation des présentations PowerPoint, Lync Server 2013 utilise Office Web Apps Server pour gérer les présentations PowerPoint. Cette nouvelle approche offre aussi, entre autres avantages, les capacités suivantes :

  - Meilleure résolution d'affichage et meilleure prise en charge des capacités de PowerPoint, telles que les animations, les transitions de diapositives et la vidéo incorporée.

  - Des appareils mobiles supplémentaires peuvent accéder à ces présentations, car Lync Server 2013 utilise les langages DHTML et JavaScript standard pour diffuser des présentations PowerPoint au lieu du DHTML personnalisé et de Silverlight.

  - Les utilisateurs qui disposent des privilèges appropriés peuvent parcourir une présentation PowerPoint indépendante de la présentation elle-même. Par exemple, Ken Myler peut présenter son diaporama et Pilar Ackerman peut le parcourir et afficher n'importe quelle diapositive sans affecter la présentation de Ken.

Pour en savoir plus sur la configuration de Lync Server 2013 en vue de l’utilisation de Office Web Apps Server, consultez la rubrique [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902).

## Utilisation d'Office Web Apps Server par les utilisateurs pour consulter des fichiers Office dans des dossiers partagés et des sites web à l'aide des visionneuses en ligne

Les visionneuses en ligne permettent aux utilisateurs d'utiliser un navigateur web pour consulter des fichiers Excel, PowerPoint et Word stockés sur les serveurs web ou les dossiers partagés d'une organisation. Les utilisateurs peuvent très facilement consulter des fichiers Office dans un navigateur web sans avoir à ouvrir une autre application. Par ailleurs, les visionneuses en ligne ne nécessitent pas l'installation de Office 2013 sur les ordinateurs des utilisateurs. Elles génèrent aussi le code requis pour lier ou incorporer l'URL au sein d'une page web. Vous pouvez les utiliser dans votre intranet ou sur Internet.

Office Web Apps Server fournit une page à l'adresse http://*OfficeWebAppsServername*/op/generate.aspx que vous pouvez utiliser pour générer des liens vers des documents accessibles publiquement à l'aide d'une adresse UNC ou URL. Lorsqu'un utilisateur choisit une URL générée, les visionneuses en ligne permettent à Office Web Apps Server d'accéder au fichier et de l'afficher à l'aide d'Office Web Apps. L'utilisateur peut consulter le fichier Word, Excel, ou PowerPoint dans un navigateur avec exactement les mêmes fonctionnalités Office. La mise en forme et la mise en page des documents Word sont préservées, les données des classeurs Excel peuvent être filtrées et triées, et les animations des présentations PowerPoint fonctionnent. Toutefois, retenez que les visionneuses en ligne permettent à l'utilisateur d'afficher et non de modifier les fichiers, et qu'elles ne sont pas en mesure d'ouvrir les fichiers qui demandent une authentification.

Pour plus d'informations sur les visionneuses en ligne, consultez la rubrique [Planning for Online Viewers with Office Web Apps Server](plan-office-web-apps-server.md).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft héberge une version exclusivement destinée à Internet de Création d'une URL sur <a href="http://go.microsoft.com/fwlink/?linkid=256548">Office.com</a>.</td>
</tr>
</tbody>
</table>


## Voir aussi


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Planification d'Office Web Apps Server](plan-office-web-apps-server.md)  
[Déployer Office Web Apps Server](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)

