---
title: "CTokenGroups Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenGroups"
  - "ATL.CTokenGroups"
  - "CTokenGroups"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenGroups class"
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CTokenGroups Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für die **TOKEN\_GROUPS**\-Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CTokenGroups  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](../Topic/CTokenGroups::CTokenGroups.md)|Der \-Konstruktor.|  
|[CTokenGroups::~CTokenGroups](../Topic/CTokenGroups::~CTokenGroups.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTokenGroups::Add](../Topic/CTokenGroups::Add.md)|Fügt `CSid` oder vorhandene Eine **TOKEN\_GROUPS**\-Struktur dem `CTokenGroups`\-Objekt hinzu.|  
|[CTokenGroups::Delete](../Topic/CTokenGroups::Delete.md)|Löscht `CSid` und die zugehörigen Attribute vom `CTokenGroups`\-Objekt.|  
|[CTokenGroups::DeleteAll](../Topic/CTokenGroups::DeleteAll.md)|Löscht alle `CSid`\-Objekte und ihre zugeordneten Attribute vom `CTokenGroups`\-Objekt.|  
|[CTokenGroups::GetCount](../Topic/CTokenGroups::GetCount.md)|Gibt die Anzahl der `CSid`\-Objekten und zugeordneten Attribute zurück, die im **CTokenGroups** \- Objekt enthalten sind.|  
|[CTokenGroups::GetLength](../Topic/CTokenGroups::GetLength.md)|Gibt die Größe des `CTokenGroups`\-Objekts zurück.|  
|[CTokenGroups::GetPTOKEN\_GROUPS](../Topic/CTokenGroups::GetPTOKEN_GROUPS.md)|Ruft einen Zeiger auf die **TOKEN\_GROUPS**\-Struktur ab.|  
|[CTokenGroups::GetSidsAndAttributes](../Topic/CTokenGroups::GetSidsAndAttributes.md)|Ruft die `CSid`\-Objekte und Attribute ab, die dem `CTokenGroups`\-Objekt gehören.|  
|[CTokenGroups::LookupSid](../Topic/CTokenGroups::LookupSid.md)|Ruft die Attribute ab, die einem `CSid`\-Objekt zugeordnet werden.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTokenGroups::operator const TOKEN\_GROUPS \*](../Topic/CTokenGroups::operator%20const%20TOKEN_GROUPS%20*.md)|Wandelt das `CTokenGroups`\-Objekt in einen Zeiger auf eine Struktur **TOKEN\_GROUPS** um.|  
|[CTokenGroups::operator \=](../Topic/CTokenGroups::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und wird zu jedem Benutzer zugeordnet, der auf ein Windows NT\- oder Windows 2000system protokolliert wird.  
  
 Die **CTokenGroups**\-Klasse ist ein Wrapper für die [TOKEN\_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)\-Struktur und enthält Informationen über die Gruppensicherheits\-id \(SID\) in einem Zugriffstoken.  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [Beispiel für die Sicherheit](../../top/visual-cpp-samples.md)   
 [CSid Class](../../atl/reference/csid-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)