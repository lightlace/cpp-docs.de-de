---
title: "CUrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CUrl"
  - "CUrl"
  - "ATL::CUrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUrl class"
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CUrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine URL dar.  Sie ermöglicht es Ihnen, um jedes Element des URL unabhängig von anderen zu bearbeiten, ob, eine vorhandene URL\-Zeichenfolge analysieren oder eine Zeichenfolge von Grund auf neu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CUrl  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CUrl::CUrl](../Topic/CUrl::CUrl.md)|Der \-Konstruktor.|  
|[CUrl::~CUrl](../Topic/CUrl::~CUrl.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CUrl::Canonicalize](../Topic/CUrl::Canonicalize.md)|Rufen Sie diese Methode auf, um die URL\-Zeichenfolge zur kanonischen Form zu konvertieren.|  
|[CUrl::Clear](../Topic/CUrl::Clear.md)|Rufen Sie diese Methode auf, um alle URL\-Felder zu löschen.|  
|[CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md)|Rufen Sie diese Methode auf, um die URL zu decodieren und zu analysieren.|  
|[CUrl::CreateUrl](../Topic/CUrl::CreateUrl.md)|Rufen Sie diese Methode auf, um die URL zu erstellen.|  
|[CUrl::GetExtraInfo](../Topic/CUrl::GetExtraInfo.md)|Rufen Sie diese Methode auf, um weitere Informationen abzurufen \(wie?*Text* oder \#text\) aus der URL.|  
|[CUrl::GetExtraInfoLength](../Topic/CUrl::GetExtraInfoLength.md)|Rufen Sie diese Methode auf, um die Länge der zusätzlichen Informationen abzurufen \(wie? aus der URL abzurufen *Text* oder \#text\).|  
|[CUrl::GetHostName](../Topic/CUrl::GetHostName.md)|Rufen Sie diese Methode auf, um den Hostnamen vom URL abzurufen.|  
|[CUrl::GetHostNameLength](../Topic/CUrl::GetHostNameLength.md)|Rufen Sie diese Methode auf, um die Länge des Hostnamens abzurufen.|  
|[CUrl::GetPassword](../Topic/CUrl::GetPassword.md)|Rufen Sie diese Methode auf, um das Kennwort im URL abzurufen.|  
|[CUrl::GetPasswordLength](../Topic/CUrl::GetPasswordLength.md)|Rufen Sie diese Methode auf, um die Länge des Kennworts abzurufen.|  
|[CUrl::GetPortNumber](../Topic/CUrl::GetPortNumber.md)|Rufen Sie diese Methode auf, um die Portnummer im Hinblick auf ATL\_URL\_PORT abzurufen.|  
|[CUrl::GetScheme](../Topic/CUrl::GetScheme.md)|Rufen Sie diese Methode auf, um das URL\-Schema abzurufen.|  
|[CUrl::GetSchemeName](../Topic/CUrl::GetSchemeName.md)|Rufen Sie diese Methode auf, um den URL\-Schemanamen abzurufen.|  
|[CUrl::GetSchemeNameLength](../Topic/CUrl::GetSchemeNameLength.md)|Rufen Sie diese Methode auf, um die Länge des URL\-Schemanamens abzurufen.|  
|[CUrl::GetUrlLength](../Topic/CUrl::GetUrlLength.md)|Rufen Sie diese Methode auf, um die URL\-Länge abzurufen.|  
|[CUrl::GetUrlPath](../Topic/CUrl::GetUrlPath.md)|Rufen Sie diese Methode auf, um den URL\-Pfad abzurufen.|  
|[CUrl::GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md)|Rufen Sie diese Methode auf, um die URL\-Pfadlänge abzurufen.|  
|[CUrl::GetUserName](../Topic/CUrl::GetUserName.md)|Rufen Sie diese Methode auf, um den Benutzernamen aus dem URL abzurufen.|  
|[CUrl::GetUserNameLength](../Topic/CUrl::GetUserNameLength.md)|Rufen Sie diese Methode auf, um die Länge des Benutzernamens abzurufen.|  
|[CUrl::SetExtraInfo](../Topic/CUrl::SetExtraInfo.md)|Rufen Sie diese Methode auf, um die zusätzlichen Informationen festzulegen \(wie?*Text* oder \#text\) der URL.|  
|[CUrl::SetHostName](../Topic/CUrl::SetHostName.md)|Rufen Sie diese Methode auf, um den Hostnamen festzulegen.|  
|[CUrl::SetPassword](../Topic/CUrl::SetPassword.md)|Rufen Sie diese Methode auf, um das Kennwort festzulegen.|  
|[CUrl::SetPortNumber](../Topic/CUrl::SetPortNumber.md)|Rufen Sie diese Methode auf, um die Portnummer im Hinblick auf ATL\_URL\_PORT festzulegen.|  
|[CUrl::SetScheme](../Topic/CUrl::SetScheme.md)|Rufen Sie diese Methode auf, um das URL\-Schema festzulegen.|  
|[CUrl::SetSchemeName](../Topic/CUrl::SetSchemeName.md)|Rufen Sie diese Methode auf, um den URL\-Schemanamen festzulegen.|  
|[CUrl::SetUrlPath](../Topic/CUrl::SetUrlPath.md)|Rufen Sie diese Methode auf, um den URL\-Pfad festzulegen.|  
|[CUrl::SetUserName](../Topic/CUrl::SetUserName.md)|Rufen Sie diese Methode auf, um den Benutzernamen festzulegen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CUrl::operator \=](../Topic/CUrl::operator%20=.md)|Weist das angegebene `CUrl`\-Objekt auf den aktuellen `CUrl`\-Objekt zu.|  
  
## Hinweise  
 `CUrl` ermöglicht es Ihnen, die Felder einer URL, wie der Pfad oder die Portnummer zu bearbeiten.  `CUrl` versteht URL der folgenden Form:  
  
 \<Scheme\>: \/\<UserName\>:\<Password\>@\<HostName\>:\<PortNumber\>\/\<UrlPath\>\<ExtraInfo\>  
  
 \(Einige Felder sind optional.\) Nehmen Sie diese URL:  
  
 http:\/\/someone:secret@www.microsoft.com:80\/visualc\/stuff.htm\#contents  
  
 [CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md) analysiert sie, wie folgt:  
  
-   Schema: "http" oder [ATL\_URL\_SCHEME\_HTTP](../Topic/ATL_URL_SCHEME.md)  
  
-   Benutzername: "Person"  
  
-   Kennwort: "geheimem Schlüssel"  
  
-   Hostname: "www.microsoft.com"  
  
-   PortNumber: 80  
  
-   UrlPath: "visualc\/stuff.htm"  
  
-   ExtraInfo: "\#contents"  
  
 Um das UrlPath\-Feld zu bearbeiten \(zum Beispiel\), würden Sie [GetUrlPath](../Topic/CUrl::GetUrlPath.md), [GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md) und [SetUrlPath](../Topic/CUrl::SetUrlPath.md) verwenden.  Sie würden [CreateUrl](../Topic/CUrl::CreateUrl.md) verwenden, um die vollständige URL\-Zeichenfolge zu erstellen.  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)