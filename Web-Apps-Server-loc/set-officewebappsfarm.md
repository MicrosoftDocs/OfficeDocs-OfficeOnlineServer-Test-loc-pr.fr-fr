---
title: Set-OfficeWebAppsFarm
TOCTitle: Set-OfficeWebAppsFarm
ms:assetid: 6b0b434f-5d19-4e63-9296-cf104b2f3da8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219442(v=office.15)
ms:contentKeyID: 49645212
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsFarm

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Configure les paramètres d'une batterie Office Web Apps Server existante.

## Syntaxe

    Set-OfficeWebAppsFarm [-AllowCEIP <SwitchParameter>] [-AllowHttp <SwitchParameter>] [-AllowHttpSecureStoreConnections <SwitchParameter>] [-CacheLocation <String>] [-CacheSizeInGB <Nullable>] [-CertificateName <String>] [-ClipartEnabled <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DocumentInfoCacheSize <Nullable>] [-EditingEnabled <SwitchParameter>] [-ExcelAllowExternalData <SwitchParameter>] [-ExcelConnectionLifetime <Nullable>] [-ExcelExternalDataCacheLifetime <Nullable>] [-ExcelPrivateBytesMax <Nullable>] [-ExcelRequestDurationMax <Nullable>] [-ExcelSessionTimeout <Nullable>] [-ExcelWarnOnDataRefresh <SwitchParameter>] [-ExcelWorkbookSizeMax <Nullable>] [-ExternalURL <String>] [-FarmOU <String>] [-Force <SwitchParameter>] [-InternalURL <String>] [-LogLocation <String>] [-LogRetentionInDays <Nullable>] [-LogVerbosity <String>] [-MaxMemoryCacheSizeInMB <Nullable>] [-MaxTranslationCharacterCount <Nullable>] [-OpenFromUncEnabled <SwitchParameter>] [-OpenFromUrlEnabled <SwitchParameter>] [-OpenFromUrlThrottlingEnabled <SwitchParameter>] [-PicturePasteDisabled <SwitchParameter>] [-Proxy <String>] [-RecycleActiveProcessCount <Nullable>] [-RemovePersonalInformationFromLogs <SwitchParameter>] [-RenderingLocalCacheLocation <String>] [-SSLOffloaded <SwitchParameter>] [-TranslationEnabled <SwitchParameter>] [-TranslationServiceAddress <String>] [-TranslationServiceAppId <String>] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **Set-OfficeWebAppsFarm** configure les paramètres d'une batterie Office Web Apps Server existante.

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
<td><p><strong>AllowCEIP</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active la création de rapports pour le programme d'amélioration du produit sur tous les serveurs de la batterie Office Web Apps Server.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie de serveurs Office Web Apps Server pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>AllowHttp</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indique que les sites IIS doivent être mis en service sur le port 80 pour l'accès HTTP. Utilisez <strong>AllowHTTP</strong> uniquement dans les environnements où tous les ordinateurs requièrent IPsec (chiffrement intégral) ou dans les environnements de test qui ne contiennent pas de fichiers sensibles.</p>
<p>Activé automatiquement quand vous activez <strong>SSLOffloaded</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHttpSecureStoreConnections</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indique que les connexions à la Banque d'informations sécurisée peuvent être effectuées à l'aide de connexions non SSL (par exemple, HTTP). La valeur par défaut est <strong>False</strong>.</p>
<p>Utilisez <strong>AllowHTTPSecureStoreConnections</strong> uniquement dans les environnements où tous les ordinateurs nécessitent la sécurité IPsec (chiffrement intégral) ou dans les environnements de test qui ne contiennent pas de fichiers sensibles.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheLocation</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'emplacement du cache disque global utilisé pour stocker les fichiers image rendus. L'emplacement par défaut est <strong>%programdata%\Microsoft\OfficeWebApps\Working\d\</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheSizeInGB</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la taille maximale du cache disque global en Go.</p>
<p>Le type doit être une valeur entière comprise dans la plage <strong>0</strong> à tout entier positif. La taille par défaut s'élève à <strong>15</strong> Go.</p></td>
</tr>
<tr class="even">
<td><p><strong>CertificateName</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le nom convivial du certificat que Office Web Apps Server utilise pour créer des liaisons HTTPS.</p>
<p>Si le certificat spécifié est introuvable ou a expiré, ou si la valeur spécifiée est associée à plusieurs certificats, une erreur est consignée dans le journal et la batterie n'est pas créée.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cette valeur est utilisée sur chaque serveur qui joint la batterie Office Web Apps Server. Par conséquent, chaque serveur inclus dans la batterie doit comporter un certificat portant ce nom convivial.</td>
</tr>
</tbody>
</table>

</div>
<p>Il n'est pas nécessaire de spécifier le paramètre <strong>CertificateName</strong> si vous utilisez le paramètre <strong>AllowHttp</strong> ou <strong>SSLOffloaded</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>ClipartEnabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active la prise en charge de l'insertion d'une image clipart à partir d'Office.com dans des documents Office. Cette fonctionnalité requiert une communication entre le serveur et le web, configurée soit directement, soit à l'aide d'un proxy que vous spécifiez à l'aide du paramètre <strong>Proxy</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DocumentInfoCacheSize</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie le nombre maximal d'enregistrements de conversion de documents stockés dans un cache mémoire.</p>
<p>La valeur par défaut s'élève à <strong>5 000</strong> enregistrements.</p></td>
</tr>
<tr class="even">
<td><p><strong>EditingEnabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active la prise en charge des modifications dans le navigateur. La valeur par défaut est <strong>False</strong>. Prend uniquement la valeur <strong>True</strong> si vous disposez de la licence appropriée pour utiliser la fonctionnalité de modification.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelAllowExternalData</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active l'actualisation des données externes prises en charge dans les classeurs Excel Web App qui contiennent des connexions de données externes. La valeur par défaut est <strong>True</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelConnectionLifetime</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la durée, en secondes, des connexions de données externes pour Excel Web App. La valeur par défaut est <strong>1 800</strong> secondes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelExternalDataCacheLifetime</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la durée de vie, en secondes, du cache de données externes dans Excel Web App. La valeur par défaut est <strong>300</strong> secondes.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelPrivateBytesMax</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie le nombre maximal d'octets privés, en mégaoctets, utilisés par Excel Web App. Quand la valeur est <strong>-1</strong>, le nombre maximal d'octets privés utilise 50 % de la mémoire physique de l'ordinateur.</p>
<p>Le type doit être <strong>-1</strong> ou tout entier positif. La valeur par défaut est <strong>-1</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelRequestDurationMax</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la durée maximale, en secondes, d'une demande unique dans une session. Une fois ce délai passé, la demande expire.</p>
<p>Le type doit être <strong>-1</strong> (illimité) ou un entier compris entre <strong>1</strong> et <strong>2 073 600</strong>. La valeur par défaut est <strong>300</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelSessionTimeout</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la durée, en secondes, pendant laquelle une session reste active dans Excel Web App en l'absence d'activité de l'utilisateur. Les valeurs valides comprennent les suivantes :</p>
<p><strong>-1</strong>, la session n'expire jamais</p>
<p><strong>0</strong>, la session expire à la fin d'une demande unique</p>
<p><strong>1</strong> à <strong>2073600</strong>, la session reste active entre 1 seconde et 24 jours. La valeur par défaut est <strong>450</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelWarnOnDataRefresh</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active ou désactive la boîte de dialogue d'avertissement qui s'affiche quand les données sont actualisées dans Excel Web App.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelWorkbookSizeMax</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la taille maximale, en mégaoctets, d'un classeur qu'un utilisateur peut charger.</p>
<p>Le type doit être une valeur entière comprise entre <strong>1</strong> et <strong>2000</strong>. La valeur par défaut est <strong>10</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalURL</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie la racine de l'URL que les clients utilisent pour accéder à la batterie Office Web Apps Server à partir d'Internet. Dans le cas d'une batterie Office Web Apps Server à charge équilibrée et multiserveur, l'URL externe est liée à l'adresse IP de l'équilibrage de charge externe.</p>
<p>Une batterie de serveurs Office Web Apps Server nécessite au moins une URL, définie avec soit <strong>ExternalURL</strong>, soit <strong>InternalURL</strong>. Vous pouvez également définir à la fois une URL interne et une URL externe.</p></td>
</tr>
<tr class="even">
<td><p><strong>FarmOU</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie le nom de l'unité d'organisation Active Directory dont les serveurs doivent être membres pour joindre la batterie Office Web Apps Server. Utilisez ce paramètre pour empêcher les serveurs non autorisés (c'est-à-dire, les serveurs qui ne sont pas dans l'unité d'organisation) de joindre une batterie Office Web Apps Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fait disparaître toutes les invites utilisateur en répondant « Oui ».</p></td>
</tr>
<tr class="even">
<td><p><strong>InternalURL</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie la racine de l'URL que les clients doivent utiliser pour accéder à la batterie de serveurs Office Web Apps Server depuis l'intranet.</p>
<p>Une batterie de serveurs Office Web Apps Server nécessite au moins une URL. Cette dernière est définie avec soit <strong>ExternalURL</strong>, soit <strong>InternalURL</strong>. Vous pouvez également définir à la fois une URL interne et une URL externe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogLocation</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'emplacement sur l'ordinateur local dans lequel les journaux d'activité sont stockés.</p>
<p>L'emplacement s'applique pour chaque serveur inclus dans la batterie et n'est pas personnalisable par serveur. L'emplacement par défaut est <strong>%programdata%\Microsoft\OfficeWebApps\Data\Logs\ULS\.</strong></p>
<p>Veillez à prévoir suffisamment d'espace disque sur le lecteur où sont stockés les journaux.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>LogRetentionInDays</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie le nombre de jours pendant lesquels les entrées de journal sont stockées. Les entrées de journal antérieures à la date configurée sont tronquées.</p>
<p>Le type doit être une valeur entière comprise entre <strong>0</strong> et <strong>365</strong>. La valeur par défaut est <strong>7</strong> jours.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>LogVerbosity</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie la quantité d'informations stockées dans les fichiers journaux de suivi. Les valeurs sont les suivantes :</p>
<p><strong>VerboseEX</strong> : permet d'écrire un niveau de détails bas dans le fichier journal de suivi. Utile pour les suivis pouvant atteindre de gros volumes.</p>
<p><strong>Verbose</strong> : permet d'écrire un niveau de détails bas dans le fichier journal de suivi.</p>
<p><strong>Medium</strong> : permet d'écrire un niveau de détails moyen dans le fichier journal de suivi.</p>
<p><strong>High</strong> : permet d'écrire un niveau de détails élevé dans le fichier journal de suivi.</p>
<p><strong>Monitorable</strong> : permet d'écrire des suivis qui représentent un chemin d'accès à un code inhabituel et des actions à surveiller.</p>
<p><strong>Unexpected</strong> : permet d'écrire des suivis qui représentent un chemin d'accès à un code inattendu et des actions à surveiller.</p>
<p><strong>None</strong> : permet de n'écrire aucune information de suivi dans le fichier journal de suivi.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Le fait de laisser le paramètre <strong>LogVerbosity</strong> configuré à un niveau bas pendant longtemps a un impact négatif sur les performances.</td>
</tr>
</tbody>
</table>

</div>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>MaxMemoryCacheSizeInMB</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie la quantité maximale de mémoire (en Mo) que le cache de rendu peut utiliser.</p>
<p>Le type doit être une valeur entière comprise dans la plage <strong>0</strong> à tout entier positif. La taille par défaut s'élève à <strong>1 024</strong> Mo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxTranslationCharacterCount</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie le nombre maximal de caractères d'un document à traduire.</p>
<p>Le type doit être une valeur entière. Il peut s'agir de la valeur 0 pour indiquer l'absence de limite ou d'une valeur comprise entre <strong>2 000</strong> et <strong>2 000 000</strong>. La valeur par défaut est <strong>125 000</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUncEnabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active ou désactive la possibilité d'utiliser des visionneuses en ligne pour afficher des fichiers Office à partir d'un chemin d'accès UNC.</p>
<p>Vous devez d'abord affecter la valeur True à OpenFromUrlEnabled pour permettre aux visionneuses en ligne d'afficher les fichiers situés dans les chemins d'accès UNC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenFromUrlEnabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Active ou désactive la possibilité d’utiliser des visionneuses en ligne pour afficher des fichiers Office à partir d’un chemin d’accès UNC ou d’URL.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUrlThrottlingEnabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Limite le nombre de requêtes d'ouverture depuis une URL à partir d'un serveur donné pendant une période spécifique. Les valeurs de limitation par défaut, qui ne sont pas configurables, permettent de s'assurer qu'une batterie de serveurs Office Web Apps Server ne peut pas saturer un serveur unique en demandant l'affichage de contenus dans les visionneuses en ligne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PicturePasteDisabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Permet ou empêche les utilisateurs de coller des images à partir d'une page web dans Office Web Apps. La valeur par défaut est <strong>False</strong>. Si <strong>OpenFromURLEnabled</strong> a la valeur <strong>True</strong> et si <strong>PicturePasteDisabled</strong> n'est pas défini ou a la valeur <strong>False</strong>, les utilisateurs peuvent coller des images dans Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><strong>Proxy</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'URL du serveur proxy configuré pour autoriser les requêtes HTTP faites à des sites externes. Généralement configuré conjointement aux paramètres <strong>ClipartEnabled</strong> et <strong>TranslationEnabled</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecycleActiveProcessCount</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Nullable</p></td>
<td><p>Spécifie le nombre de fichiers qu'un processus unique Word ou PowerPoint peut rendre avant que le processus ne soit recyclé.</p>
<p>Le type doit être une valeur entière comprise entre <strong>1</strong> et <strong>1 000</strong>. La valeur par défaut est <strong>5</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>RemovePersonalInformationFromLogs</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fournit un effacement conseillé des informations personnelles à partir de journaux Office Web Apps Server et remplace les valeurs par un hachage SHA256. Les informations potentiellement effacées peuvent être les suivantes :</p>
<ul>
<li><p>Noms des documents et URL</p></li>
<li><p>Adresses IP</p></li>
<li><p>Adresses de messagerie</p></li>
<li><p>Noms d'utilisateur</p></li>
</ul>
<p>La valeur par défaut est <strong>False</strong>. Notez que l'activation de ce paramètre ne garantit pas que les informations personnelles ne seront pas consignées dans les journaux Office Web Apps Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RenderingLocalCacheLocation</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'emplacement du cache temporaire utilisé par les services d'affichage Word et PowerPoint.</p>
<p>L'emplacement par défaut est <strong>%programdata%\Microsoft\OfficeWebApps\Working\waccache\</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SSLOffloaded</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indique aux serveurs inclus dans la batterie Office Web Apps Server que le protocole SSL est déchargé sur l'équilibrage de charge. Lorsque le paramètre <strong>SSLOffloaded</strong> est activé, les applications web sont liées au port 80 (HTTP) sur le serveur local. Cependant, le langage HTML qui référence d'autres ressources, comme des styles CSS ou des images, utilise des URL HTTPS pour ces références.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationEnabled</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Active la prise en charge de la traduction automatique des documents à l'aide de Microsoft Translator, un service en ligne qui permet de traduire du texte d'une langue vers une autre. Le fichier traduit s'affiche dans Word Web App. Étant donné que Microsoft Translator est un service en ligne, vous devez activer la communication entre le serveur et le web directement ou à l'aide d'un proxy que vous spécifiez à l'aide du paramètre <strong>Proxy</strong>.<br />
Microsoft Translator peut collecter des données afin d'améliorer la qualité des traductions.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>TranslationServiceAddress</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'URL du serveur de traduction auquel les demandes de traduction sont envoyées. La valeur par défaut correspond au service en ligne Microsoft Translator. En règle générale, vous n'êtes pas censé utiliser ce paramètre, sauf si vous devez changer de service de traduction.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous devez redémarrer chaque serveur de la batterie de serveurs Office Web Apps Server pour que cette modification prenne effet.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationServiceAppId</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p>Spécifie l'ID d'application du service de traduction. La valeur par défaut est celle de l'ID d'application public de Office Web Apps. En règle générale, vous n'êtes pas censé utiliser ce paramètre, sauf si vous avez négocié des services supplémentaires auprès de Microsoft Translator et qu'un ID d'application privé vous a été attribué.</p></td>
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

\------------------EXEMPLE 1---------------------

    Set-OfficeWebAppsFarm -ClipartEnabled:$true

Cet exemple montre comment activer l'insertion d'une image clipart depuis Office.com.

\------------------EXEMPLE 2---------------------

    Set-OfficeWebAppsFarm -EditingEnabled:$true

Cet exemple montre comment activer la fonctionnalité de modification pour Office Web Apps.

\------------------EXEMPLE 3---------------------

    Set-OfficeWebAppsFarm -OpenFromUncEnabled:$false

Cet exemple montre comment empêcher d'afficher un fichier Office à partir d'un chemin d'accès UNC.

## Voir aussi


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

