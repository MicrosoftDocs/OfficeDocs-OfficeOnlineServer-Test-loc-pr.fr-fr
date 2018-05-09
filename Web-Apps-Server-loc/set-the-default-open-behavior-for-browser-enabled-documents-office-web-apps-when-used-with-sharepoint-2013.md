---
title: Configuration du comportement d’ouverture par défaut des documents activés pour le navigateur (Office Web Apps dans le cadre d’une utilisation avec SharePoint 2013)
TOCTitle: Configuration du comportement d’ouverture par défaut des documents activés pour le navigateur
ms:assetid: e27e0bc8-5fb5-4bb1-8157-d7c90654175e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Ee837425(v=office.15)
ms:contentKeyID: 50181162
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Configuration du comportement d’ouverture par défaut des documents activés pour le navigateur (Office Web Apps dans le cadre d’une utilisation avec SharePoint 2013)

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2016-12-16_

**Résumé :** décrit comment configurer le comportement d'ouverture par défaut pour les documents Office dans les collections de sites et bibliothèques de documents SharePoint.

**Public concerné :** professionnels de l’informatique

Pour ouvrir un document dans une bibliothèque de documents SharePoint 2013, cliquez sur son titre. Ce qui se produit ensuite (si le fichier s’ouvre dans une application cliente ou dans le navigateur) dépend de plusieurs facteurs, tels que le type de fichier concerné, la configuration de votre batterie de serveurs Office Web Apps Server, la définition des paramètres de la fonctionnalité OpenInClient de la bibliothèque ou la collection de sites. Les étapes suivantes vous montrent comment configurer le comportement d’ouverture par défaut des documents Office lorsque SharePoint 2013 est configuré pour utiliser Office Web Apps Server.

## Définir le mode d’ouverture des documents à partir des bibliothèques SharePoint 2013

Par défaut, une fois SharePoint 2013 configuré pour utiliser Office Web Apps Server, les fichiers Word, PowerPoint, Excel ou OneNote s’ouvrent dans le navigateur lorsque vous cliquez dessus. Les documents PDF s’ouvrent dans Word Web App Web App. Il existe deux méthodes pour modifier le comportement par défaut de façon à ce que les fichiers s’ouvrent dans les applications clientes (ou le lecteur PDF par défaut) à la place :

  - **Pour la batterie de serveurs SharePoint 2013**   Vous pouvez ajuster le comportement d’ouverture par défaut en fonction du type de fichier pour la batterie de serveurs SharePoint 2013 à l’aide des cmdlets [New-SPWOPIBinding](new-spwopibinding.md) et [Set-SPWOPIBinding](set-spwopibinding.md)Windows PowerShell. Ces cmdlets peuvent également être utilisées pour [ajuster le comportement des documents PDF](http://go.microsoft.com/fwlink/p/?linkid=330246).

  - **Dans les collections de sites ou les bibliothèques de documents**   Les administrateurs et les utilisateurs d’une collection de sites peuvent utiliser la fonctionnalité OpenInClient dans SharePoint 2013 pour indiquer si les fichiers Office doivent être ouverts dans l’application cliente ou dans le navigateur. Les utilisateurs peuvent modifier ce paramètre dans les propriétés de bibliothèque de documents, et les administrateurs de collection de sites peuvent le modifier dans Administration de la collection de sites ou à l’aide de la cmdlet [Enable-SPFeature](https://technet.microsoft.com/fr-fr/library/ff607803\(v=office.15\)) pour activer la fonctionnalité OpenInClient. Consultez la section suivante pour découvrir les différentes méthodes d’activation de la fonctionnalité OpenInClient .

En général, la fonctionnalité OpenInClient remplace les liaisons WOPI que vous avez définies entre SharePoint 2013 et Office Web Apps Server. Autrement dit, si la fonctionnalité OpenInClient d’une bibliothèque ou d’une collection de sites SharePoint 2013 est activée, les documents s’ouvrent dans l’application cliente, même si le serveur SharePoint 2013 est configuré pour utiliser Office Web Apps Server.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>La configuration du comportement d’ouverture par défaut des documents activés pour le navigateur n’aura pas d’incidence sur la possibilité pour les utilisateurs de se servir des fonctionnalités <strong>Extraire</strong> et <strong>Envoyer à</strong> de SharePoint 2013 pour télécharger des documents. Pour plus d’informations sur la configuration de l’extraction, le téléchargement et l’affichage des autorisations dans SharePoint 2013, voir <a href="https://technet.microsoft.com/fr-fr/library/cc262939(v=office.15)">Planification des autorisations pour les sites et le contenu dans SharePoint 2013</a>.</td>
</tr>
</tbody>
</table>


## Définir la fonctionnalité OpenInClient pour une collection de sites ou une bibliothèque de documents

Utilisez l’une des procédures suivantes pour définir la fonctionnalité OpenInClient dans SharePoint 2013.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Certaines de ces procédures utilisent SharePoint 2013 Management Shell pour exécuter les cmdlets SharePoint. Si vous utilisez la console Windows PowerShell, vous devez ajouter le composant logiciel enfichable Microsoft.SharePoint.PowerShell à l’aide de la cmdlet <strong>Add-PSSnapin</strong>. Pour plus d’informations sur l’utilisation de Windows PowerShell avec SharePoint 2013, voir <a href="use-windows-powershell-to-administer-sharepoint-2013.md">Utiliser Windows PowerShell pour administrer SharePoint 2013</a>.</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous pouvez exécuter des tâches dans suites Office 2013 au moyen d’une souris, de raccourcis clavier ou d’entrées tactiles. Pour plus d’informations sur l’utilisation des raccourcis clavier et des entrées tactiles avec les produits et services Office, voir <a href="http://go.microsoft.com/fwlink/p/?linkid=249150">Raccourcis clavier</a> et <a href="http://go.microsoft.com/fwlink/p/?linkid=253163">Guide des fonctions tactiles dans Office</a>.</td>
</tr>
</tbody>
</table>


 **Définir la fonctionnalité OpenInClient pour les collections de sites**

1.  Dans la collection de sites SharePoint, sélectionnez l’icône **Paramètres**, puis **Paramètres du site**.

2.  Dans la page **Paramètres du site**, sous **Administration de la collection de sites**, sélectionnez **Fonctionnalités de la collection de sites**.

3.  Sur la page **Fonctionnalités**, sous **Ouvrir par défaut des documents dans des applications clientes**, sélectionnez **Activer** (la fonctionnalité OpenInClient est activée) pour ouvrir les documents dans l’application cliente. Sélectionnez **Désactiver** (la fonctionnalité OpenInClient est désactivée) pour ouvrir les documents dans le navigateur.

 **Définir le comportement d’ouverture par défaut pour les collections de sites à l’aide de Windows PowerShell**

1.  Vérifiez tout d’abord que vous disposez bien des appartenances suivantes :
    
      - Rôle serveur fixe **securityadmin** sur l’instance SQL Server.
    
      - Rôle de base de données fixe **db\_owner** sur toutes les bases de données à mettre à jour.
    
      - du groupe Administrateurs sur le serveur sur lequel vous exécutez les cmdlets Windows PowerShell.
    
    Lisez également la rubrique [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050) et ajoutez toute autre appartenance requise.
    
    Un administrateur peut utiliser la cmdlet **Add-SPShellAdmin** pour accorder des autorisations d'utilisation des cmdlets des SharePoint 2013..
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Si vous ne disposez pas des autorisations, contactez votre administrateur d’installation ou votre administrateur SQL Server afin de les demander. Pour plus d’informations sur les autorisations Windows PowerShell, voir <a href="use-windows-powershell-to-administer-sharepoint-2013.md">Permissions</a> et <a href="https://technet.microsoft.com/fr-fr/library/ff607596(v=office.15)">Add-SPShellAdmin</a>.</td>
    </tr>
    </tbody>
    </table>


2.  Ouvrez SharePoint 2013 Management Shell avec élévation de privilèges :
    
    **Dans Windows Server 2008**
    
    1.  Dans le menu **Démarrer**, sélectionnez **Tous les programmes**.
    
    2.  Sélectionnez **Produits Microsoft SharePoint 2013**.
    
    3.  Choisissez **SharePoint 2013 Management Shell** pour afficher le menu contextuel (clic droit).
    
    4.  Dans le menu contextuel, choisissez **Exécuter en tant qu’administrateur**.
    
    **Dans Windows Server 2012**
    
    1.  Effectuez un balayage en partant du bord de façon à afficher les icônes, puis choisissez **Rechercher** pour afficher toutes les applications installées sur l’ordinateur.
    
    2.  Choisissez (clic droit) **SharePoint 2013 Management Shell** pour afficher la barre de l’application.
    
    3.  Dans la barre de l'application, sélectionnez **Exécuter en tant qu'administrateur**.

3.  À l'invite de commandes Windows PowerShell, tapez l'une des commandes suivantes :
    
      - Pour activer la fonctionnalité OpenInClient pour une collection de sites spécifique (pour ouvrir les documents dans l’application cliente), entrez la commande suivante :
        
            Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
        
        où *\<SiteCollURL\>* correspond à l’URL de la collection de sites.
    
      - Pour activer la fonctionnalité OpenInClient pour toutes les collections de sites (pour ouvrir les documents dans l’application cliente), entrez la commande suivante :
        
            Get-SPSite -limit ALL |foreach{ Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }
    
      - Pour désactiver la fonctionnalité OpenInClient pour une collection de sites spécifique (pour ouvrir les documents dans le navigateur), entrez la commande suivante :
        
            Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
        
        où *\<SiteCollURL\>* correspond à l’URL de la collection de sites.
    
      - Pour désactiver la fonctionnalité OpenInClient pour toutes les collections de sites (pour ouvrir les documents dans le navigateur), entrez la commande suivante :
        
            Get-SPSite -limit ALL |foreach{ Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }

 **Définir le comportement d’ouverture par défaut pour une bibliothèque de documents à l’aide de la page de paramètres de la bibliothèque de documents**

1.  Sur la page de la bibliothèque de documents, sélectionnez l’onglet **Bibliothèque**.

2.  Dans le groupe **Paramètres**, sélectionnez **Paramètres de la bibliothèque**.

3.  Sur la page **Paramètres de la bibliothèque de documents**, sélectionnez **Paramètres avancés**.

4.  Sur la page **Paramètres avancés**, dans **Ouverture du document dans le navigateur**, sélectionnez l'une des options suivantes :
    
      - **Ouvrir dans l'application cliente**   Lorsqu'un utilisateur choisit un document dans cette bibliothèque, celui-ci s'ouvre dans l'application cliente correspondante si celle-ci est disponible.
    
      - **Ouvrir dans le navigateur**   Lorsqu'un utilisateur choisit un document dans cette bibliothèque, celui-ci s'ouvre dans le navigateur Web de l'application Web pour ce type de document. Lorsque le document est ouvert dans l'application Web, l'utilisateur peut alors décider d'ouvrir le document dans l'application cliente.
    
      - **Utiliser le paramètre par défaut du serveur**   Lorsqu’un utilisateur choisit un document dans cette bibliothèque, le document s’ouvre à l’aide du comportement d’ouverture par défaut spécifié pour le serveur exécutant SharePoint 2013.

 **Définir le comportement d’ouverture par défaut pour les bibliothèques de documents protégés par IRM à l’aide de Windows PowerShell**

1.  Vérifiez tout d’abord que vous disposez bien des appartenances suivantes :
    
      - Rôle serveur fixe **securityadmin** sur l'instance SQL Server.
    
      - Rôle de base de données fixe **db\_owner** sur toutes les bases de données à mettre à jour.
    
      - du groupe Administrateurs sur le serveur sur lequel vous exécutez les cmdlets Windows PowerShell.
    
    Lisez également la rubrique [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050) et ajoutez toute autre appartenance requise.
    
    Un administrateur peut utiliser la cmdlet **Add-SPShellAdmin** pour accorder des autorisations d'utilisation des cmdlets des SharePoint 2013..
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Si vous ne disposez pas des autorisations, contactez votre administrateur d’installation ou votre administrateur SQL Server afin de les demander. Pour plus d’informations sur les autorisations Windows PowerShell, voir <a href="use-windows-powershell-to-administer-sharepoint-2013.md">Permissions</a> et <a href="https://technet.microsoft.com/fr-fr/library/ff607596(v=office.15)">Add-SPShellAdmin</a>.</td>
    </tr>
    </tbody>
    </table>


2.  Ouvrez SharePoint 2013 Management Shell avec élévation de privilèges :
    
    **Dans Windows Server 2008**
    
    1.  Dans le menu **Démarrer**, sélectionnez **Tous les programmes**.
    
    2.  Sélectionnez **Produits Microsoft SharePoint 2013**.
    
    3.  Choisissez **SharePoint 2013 Management Shell** pour afficher le menu contextuel (clic droit).
    
    4.  Dans le menu contextuel, choisissez **Exécuter en tant qu’administrateur**.
    
    **Dans Windows Server 2012**
    
    1.  Effectuez un balayage en partant du bord de façon à afficher les icônes, puis choisissez **Rechercher** pour afficher toutes les applications installées sur l’ordinateur.
    
    2.  Choisissez (cliquez avec le bouton droit sur) **SharePoint 2013 Management Shell** pour afficher la barre de l'application.
    
    3.  Dans la barre de l'application, sélectionnez **Exécuter en tant qu'administrateur**.

3.  À l’invite de commandes Windows PowerShell, entrez la commande suivante :
    
        Get-SPWeb -site <SiteCollURL> | % {$_.Lists} | where {$_.IrmEnabled -eq $true} | % {$_.DefaultItemOpen =[Microsoft.Sharepoint.DefaultItemOpen]::<DefaultItemOpenSetting>; $_.Update()}
    
    où :
    
      - *\<SiteCollURL\>* correspond à l'URL de la collection de sites où réside la bibliothèque de documents.
    
      - *\<DefaultItemOpenSetting\>* est une valeur d’énumération **DefaultItemOpen** qui spécifie le comportement d’ouverture par défaut. **PreferClient** permet d’ouvrir les documents dans l’application cliente associée (si celle-ci est disponible). **Browser** permet d’ouvrir les documents dans le navigateur.

## Voir aussi


[Get-SPWOPIBinding](get-spwopibinding.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Windows PowerShell pour administrer SharePoint 2013](use-windows-powershell-to-administer-sharepoint-2013.md)  
[Office Web Apps Server](office-web-apps-server.md)  


[Get-SPWeb](https://technet.microsoft.com/fr-fr/library/ff607807\(v=office.15\))  
[Get-SPSite](https://technet.microsoft.com/fr-fr/library/ff607950\(v=office.15\))  
[Get-SPFeature](https://technet.microsoft.com/fr-fr/library/ff607945\(v=office.15\))

