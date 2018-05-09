---
title: New-SPWOPIBinding
TOCTitle: New-SPWOPIBinding
ms:assetid: 696f01b4-a144-431b-9bae-1c3ede78609d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219441(v=office.15)
ms:contentKeyID: 49645209
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPIBinding

 

_**Sapplique à :**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Dernière rubrique modifiée :**2015-03-09_

Crée une liaison pour associer les extensions de noms de fichiers ou les applications à leurs actions sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

## Syntaxe

    New-SPWOPIBinding -ServerName <String> [-Action <String>] [-AllowHTTP <SwitchParameter>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-FileName <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **New-SPWOPIBinding** associe les extensions de noms de fichiers ou les applications aux actions sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée. Chaque liaison vous permet d'utiliser l'application WOPI pour afficher ou modifier les fichiers dans votre bibliothèque SharePoint. Par exemple, lorsqu'un utilisateur affiche un document Word dans une liste de documents SharePoint, la liste SharePoint indiquera les options disponibles pour afficher ou modifier le document en fonction des actions qui sont liées à Word sur la batterie de serveurs SharePoint.

Pour utiliser une application WOPI, telle qu'un serveur qui exécute l'Office Web Apps Server, pour l'Office Web Apps, vous devez exécuter cette cmdlet sur la batterie SharePoint avant de pouvoir utiliser l'Office Web Apps.

Si vous exécutez **New-SPWOPIBinding** pour une application ou une extension de nom de fichier pour lesquelles la liaison (ou association) existe déjà, la cmdlet échouera.

SharePoint Management Shell

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
<th>Obligatoire</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerName</strong></p></td>
<td><p>Requis</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le nom ou le nom de domaine complet de l'application WOPI (telle qu'un serveur exécutant l'Office Web Apps Server).</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'action à lier. Par exemple, « afficher », « modifier » et « afficher en mode incorporé ». Pour obtenir une liste des actions prises en charge par l'application WOPI, exécutez <strong>Get-SPWOPIBinding</strong>. Généralement, vous n'aurez pas recours à ce paramètre. Si vous spécifiez certaines actions mais pas d'autres, certaines fonctionnalités SharePoint pourraient ne pas fonctionner.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHTTP</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Spécifie que la cmdlet peut utiliser HTTP pour découvrir ce qui est pris en charge par l'application WOPI. Si la valeur True est spécifiée, les informations de découverte à partir de l'application WOPI seront envoyées sur une connexion non sécurisée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'application à lier. Les applications possibles sont les suivantes : « Word », « Excel », « PowerPoint » ou « OneNote ». Exécutez <strong>Get-SPWOPIBinding</strong> pour obtenir la liste complète des applications prises en charge par l'application WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Gère les objets de manière à optimiser leur libération. L’utilisation d’objets, tels que <strong>SPWeb</strong> ou <strong>SPSite</strong>, peut consommer des quantités de mémoire élevées et le recours à ces objets dans des scripts Windows PowerShell implique une gestion appropriée de la mémoire. À l’aide de l’objet <strong>SPAssignment</strong>, vous pouvez affecter des objets à une variable et les libérer dès qu’ils ne sont plus nécessaires afin de libérer de la mémoire. Lorsque les objets <strong>SPWeb</strong>, <strong>SPSite</strong> ou <strong>SPSiteAdministration</strong> sont utilisés, ils sont automatiquement libérés si un ensemble d’affectations ou si le paramètre <strong>Global</strong> n’est pas utilisé.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lorsque le paramètre <strong>Global</strong> est utilisé, tous les objets sont contenus dans le magasin global. Si des objets ne sont pas utilisés immédiatement ou libérés à l’aide de la commande <strong>Stop-SPAssignment</strong>, un scénario d’insuffisance de mémoire peut se produire.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie les extensions de noms de fichiers à lier. Exécutez <strong>Get-SPWOPIBinding</strong> pour obtenir la liste des extensions de noms de fichiers prises en charge par l'application WOPI.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileName</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le chemin d'accès du fichier .xml qui contient les informations sur la découverte de l'application WOPI. Vous pouvez charger des informations de découverte à partir d'un fichier xml au lieu d'effectuer la demande directement à partir de l'application WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'identificateur programmatique (ProgID) de l'application à lier. Exécutez <strong>Get-SPWOPIBinding</strong> pour obtenir la liste des ProgID pris en charge par l'application WOPI. Vous pouvez aussi réserver ce paramètre afin d'associer une action à un dossier OneNote.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Affiche un message qui explique l’effet de la commande au lieu de l’exécuter. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\--------------EXEMPLE 1-----------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com"

Cet exemple montre comment créer les liaisons de toutes les applications et les extensions de noms de fichiers prises en charge par l'application WOPI sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

\--------------EXEMPLE 2-----------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com" -Application "Excel"

Cet exemple montre comment associer Excel à toutes les actions prises en charge par l'application WOPI pour Excel sur la batterie de serveurs SharePoint actuelle sur laquelle cette cmdlet est exécutée.

## Voir aussi


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utiliser Office Web Apps avec SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

