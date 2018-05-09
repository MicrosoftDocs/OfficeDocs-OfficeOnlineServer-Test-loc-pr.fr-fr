---
title: Utiliser Windows PowerShell pour administrer SharePoint 2013
TOCTitle: Utiliser Windows PowerShell pour administrer SharePoint 2013
ms:assetid: ae4901b4-505a-42a9-b8d4-fca778abc12e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Ee806878(v=office.15)
ms:contentKeyID: 49645230
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Utiliser Windows PowerShell pour administrer SharePoint 2013

 

_**Sapplique à :**SharePoint Foundation 2013, SharePoint Server 2013 Enterprise, SharePoint Server 2013 Standard_

_**Dernière rubrique modifiée :**2016-12-16_

**Résumé :**Découvrez les applets de commande et les concepts Windows PowerShell de base et comment utiliser Windows PowerShell avec SharePoint 2013.

Contenu de cet article :

  - Vue d’ensemble

  - Accès à Windows PowerShell pour les produits SharePoint 2013

  - Autorisations

  - Scripts et stratégies d'exécution

  - Formation à Windows PowerShell

## Vue d’ensemble

Windows PowerShell est un interpréteur de commandes et un langage de script qui fournit un accès administrateur complet aux API applicables. Les administrateurs peuvent interagir directement avec SharePoint 2013 pour manipuler les applications web, les collections de sites, les sites, les listes et bien d’autres choses encore. En outre, un administrateur peut écrire des applets de commande (prononcer « app-lette »).

Windows PowerShell 3.0 est une condition préalable à l’installation de SharePoint 2013. Il sera installé, s’il ne l’est pas déjà, lorsque vous exécutez l’Outil de préparation des produits Microsoft SharePoint. Par défaut, Windows PowerShell se trouve à l’emplacement suivant :\<%SystemRoot%\>\\System32\\WindowsPowerShell\\v1.0\\PowerShell.exe.

Pour obtenir la liste des nouvelles fonctionnalités de Windows PowerShell 3.0, voir [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=272782)

Pour consulter un outil interactif et un guide qui vous aide à apprendre la syntaxe Windows PowerShell, voir l’[outil générateur de commande de Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=229854) et le [guide de mise en route](http://www.microsoft.com/download/en/details.aspx?id=27588).

Nous vous recommandons d’utiliser Windows PowerShell pour les tâches d’administration en ligne de commande. L’outil en ligne de commande Stsadm a été abandonné, mais il est inclus pour assurer la compatibilité avec les versions précédentes.

## Accès à Windows PowerShell pour SharePoint 2013

Une fois que vous avez installé SharePoint 2013, les applets de commande Windows PowerShell applicables sont disponibles dans SharePoint 2013 Management Shell. Vous pouvez gérer la plupart des aspects de SharePoint 2013 dans SharePoint Management Shell. Vous pouvez créer des collections de sites, des applications web, des comptes d’utilisateur, des applications de service, des proxys, et bien d’autres choses encore. Les commandes que vous tapez dans SharePoint Management Shell retournent des objets SharePoint qui sont fondés sur Microsoft .NET Framework. Ces objets peuvent être appliqués comme entrées de commandes ultérieures ou stockés dans des variables locales pour une utilisation ultérieure.

Avec SharePoint Management Shell, vous ne devez pas inscrire le composant logiciel enfichable qui contient les applets de commande. L’inscription du module Microsoft.SharePoint.PowerShell.dll pour les applets de commande SharePoint 2013 est automatique, comme conséquence de la ligne `Add-PSSnapin Microsoft.SharePoint.PowerShell` du fichier SharePoint.ps1 qui est situé dans *%CommonProgramFiles%*\\Microsoft Shared\\Web Server Extensions\\15\\Config\\PowerShell\\Registration. Pour utiliser la console Windows PowerShell, vous devez inscrire manuellement ce composant logiciel enfichable.

Que vous utilisiez SharePoint Management Shell ou la console Windows PowerShell, vous pouvez également charger des composants logiciels enfichables supplémentaires. Pour plus d’informations, voir l’article relatif à la [personnalisation des profils](http://go.microsoft.com/fwlink/p/?linkid=183166).

**Pour accéder à SharePoint Management Shell**

1.  Démarrez SharePoint Management Shell.
    
      - Pour Windows Server 2008 R2 :
        
          - Cliquez sur **Démarrer**, sur **Produits Microsoft SharePoint 2013**, puis sur **SharePoint Management Shell**.
    
      - Pour Windows Server 2012 :
        
          - Sur l’écran **Démarrer**, cliquez sur **SharePoint Management Shell**.
            
            Si **SharePoint Management Shell** ne se trouve pas dans l’écran **Accueil**  :
        
        <!-- end list -->
        
          - Cliquez avec le bouton droit sur **Ordinateur**, cliquez sur **Toutes les applications**, puis sur **SharePoint Management Shell**.
    
    Pour plus d’informations sur la façon d’interagir avec Windows Server 2012, voir [Tâches de gestion courantes et navigation dans Windows Server 2012](http://technet.microsoft.com/fr-fr/library/hh831491.aspx).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SharePoint 2013 Management Shell et la console Windows PowerShell diffèrent également sur l’utilisation de l’option <code>ReuseThread</code>, qui définit l’utilisation du modèle de thread. L’utilisation de SharePoint 2013 Management Shell est définie par cette ligne, <code>{Host.Runspace.ThreadOptions = &quot;ReuseThread&quot;}</code>, qui se trouve dans le fichier SharePoint.ps1. Pour plus d’informations, voir l’article sur les <a href="http://go.microsoft.com/fwlink/p/?linkid=183145">options de thread PS</a>.</td>
</tr>
</tbody>
</table>


## Autorisations

## Sur sites

Avant de pouvoir utiliser l’applet de commande **Add-SPShellAdmin** pour accorder des autorisations aux utilisateurs afin d’exécuter des applets de commande SharePoint 2013, vérifiez que vous respectez tous les critères de configuration minimale suivants :

  - vous devez être membre du rôle serveur fixe **securityadmin** sur l’instance SQL Server ;

  - vous devez être membre du rôle de base de données fixe **db\_owner** sur toutes les bases de données à mettre à jour ;

  - vous devez être membre du groupe Administrateurs sur le serveur sur lequel vous exécutez l’applet de commande Windows PowerShell.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si vous ne disposez pas de ces autorisations, faites-en la demande auprès de votre administrateur de configuration ou administrateur SQL Server.</td>
</tr>
</tbody>
</table>


Pour plus d’informations sur Windows PowerShell, reportez-vous à Autorisations et [Add-SPShellAdmin](https://technet.microsoft.com/fr-fr/library/ff607596\(v=office.15\))

Si vous n’êtes pas membre du rôle **SharePoint\_Shell\_Access** ou du groupe local **WSS\_Admin\_WPG**, utilisez l’applet de commande **Add-SPShellAdmin** pour ajouter le groupe **WSS\_Admin\_WPG** dans tous les serveurs web frontaux de la batterie de serveurs SharePoint et le rôle **SharePoint\_Shell\_Access**. Si la base de données SQL Server ne dispose pas d’un rôle **SharePoint\_Shell\_Access**, celui-ci est automatiquement créé lorsque vous exécutez l’applet de commande **Add-SPShellAdmin**. Après avoir exécuté l’applet de commande **Add-SPShellAdmin**, les utilisateurs peuvent exécuter les applets de commande Windows PowerShell SharePoint dans un environnement de batterie de plusieurs serveurs.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lorsque vous installez SharePoint 2013, le compte d’utilisateur à partir duquel vous exécutez l’installation se voit accorder les autorisations appropriées pour exécuter les applets de commande Windows PowerShell. Si aucun utilisateur n’a été ajouté pour exécuter une applet de commande Windows PowerShell, vous pouvez utiliser l’applet de commande <strong>Add-SPShellAdmin</strong> pour l’ajouter.</td>
</tr>
</tbody>
</table>


Vous devez exécuter l’applet de commande **Add-SPShellAdmin** pour toutes les bases de données auxquelles vous voulez octroyer l’accès. Si aucune base de données n’est spécifiée, la base de données de configuration de la batterie de serveurs est utilisée. Si vous spécifiez une base de données, le contenu de la batterie de serveurs sera inclus en plus de la base de données de configuration de la batterie de serveurs que vous spécifiez.

Pour afficher une liste de toutes les applets de commande **SPShellAdmin**, à partir d’une invite de commandes Windows PowerShell, tapez `Get-Command -Noun SPShellAdmin`.

## SharePoint Online

Vérifiez que vous disposez des autorisations administratives suivantes :

  - Le rôle d’administrateur global du site SharePoint Online sur lequel vous exécutez l’applet de commande Windows PowerShell doit vous être assigné. Pour plus d’informations, voir l’article relatif aux [rôles administratifs et groupes d’utilisateurs par défaut](http://go.microsoft.com/fwlink/p/?linkid=242451).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Vous pouvez utiliser un groupe spécifique de Windows PowerShell avec SharePoint Online. Pour plus d’informations, voir <a href="https://technet.microsoft.com/fr-fr/library/fp161362(v=office.15)">Office 365 PowerShell pour SharePoint Online</a>.</td>
    </tr>
    </tbody>
    </table>


## Scripts et stratégies d’exécution

Bien que vous puissiez utiliser Windows PowerShell pour effectuer une tâche administrative unique, vous pouvez également recourir à un script pour automatiser une série de tâches. Un script est un fichier texte qui contient une ou plusieurs commandes Windows PowerShell. Les noms de scripts Windows PowerShell sont constitués de l’extension .ps1.

Pour exécuter des scripts, la stratégie d’exécution minimale requise pour SharePoint 2013 est RemoteSigned, bien que la stratégie par défaut pour Windows PowerShell soit Restricted. Si la stratégie demeure Restricted, SharePoint 2013 Management Shell changera la stratégie pour Windows PowerShell sur RemoteSigned. Cela signifie que vous devez sélectionner **Exécuter en tant qu’administrateur** pour démarrer SharePoint 2013 Management Shell avec une autorisation administrative élevée. Cette modification s’appliquera à toutes les sessions Windows PowerShell. Pour plus d’informations, voir l’[énumération ExecutionPolicy](http://go.microsoft.com/fwlink/p/?linkid=242452).

Pour obtenir plus d’informations sur les scripts et les stratégies d’exécution, voir [about\_scripts](http://go.microsoft.com/fwlink/p/?linkid=144310) et [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050) respectivement.

## Découverte de Windows PowerShell

Il existe plusieurs ressources d’apprentissage de Windows PowerShell destinées aux professionnels de l’informatique SharePoint.

**Centre de scripts TechNet**

Ce centre comprend de nombreuses ressources pour vous permettre de découvrir les notions de base sur Windows PowerShell. Il contient également des référentiels de scripts avec des exemples de scripts qui sont généralement utilisés avec différents produits Microsoft. Le tableau suivant répertorie les ressources d’apprentissage principales.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Page</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187813">Documentation Windows PowerShell sur TechNet</a></p></td>
<td><p>Cette section de la bibliothèque TechNet contient des copies web des rubriques d’aide surWindows PowerShell. La section offre également des copies web du document de Prise en main de Windows PowerShell, l’aide PowerShell.exe et une présentation de Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187815">Génération de scripts avec Windows PowerShell</a></p></td>
<td><p>Page d’accueil des ressources d’apprentissage de Windows PowerShell.</p></td>
</tr>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187817">Manuel du propriétaire Windows PowerShell</a></p></td>
<td><p>Guide web pour démarrer avec Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187819">Référence rapide Windows PowerShell</a></p></td>
<td><p>Copie téléchargeable du document de référence rapide qui est installé avec Windows PowerShell.</p></td>
</tr>
</tbody>
</table>


Au fil de votre lecture de ces ressources, il peut vous être utile de consulter les références aux applets de commande et aux concepts suivants avant de commencer à utiliser Windows PowerShell pour SharePoint 2013 :

  - [Get-Command](http://go.microsoft.com/fwlink/p/?linkid=171069)

  - [Get-Member](http://go.microsoft.com/fwlink/p/?linkid=171070)

  - [Get-Help](http://go.microsoft.com/fwlink/p/?linkid=171068)

  - [Alias](http://go.microsoft.com/fwlink/p/?linkid=113207)

  - [Tuyauterie et canalisation dans Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=187808)

  - [Jeux de paramètres d’applets de commande](http://go.microsoft.com/fwlink/p/?linkid=187810)

  - [Foreach-Object](http://go.microsoft.com/fwlink/p/?linkid=187812)

  - [Where-Object](http://go.microsoft.com/fwlink/p/?linkid=187811)

