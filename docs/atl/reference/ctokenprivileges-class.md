---
title: "CTokenPrivileges Class"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenPrivileges"
  - "CTokenPrivileges"
  - "ATL.CTokenPrivileges"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenPrivileges class"
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CTokenPrivileges Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für die **TOKEN\_PRIVILEGES**\-Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CTokenPrivileges  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](../Topic/CTokenPrivileges::CTokenPrivileges.md)|Der \-Konstruktor.|  
|[CTokenPrivileges::~CTokenPrivileges](../Topic/CTokenPrivileges::~CTokenPrivileges.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTokenPrivileges::Add](../Topic/CTokenPrivileges::Add.md)|Fügt eine oder mehrere Berechtigungen dem `CTokenPrivileges`\-Objekt hinzu.|  
|[CTokenPrivileges::Delete](../Topic/CTokenPrivileges::Delete.md)|Löscht ein rechts vom `CTokenPrivileges`\-Objekt.|  
|[CTokenPrivileges::DeleteAll](../Topic/CTokenPrivileges::DeleteAll.md)|Löscht alle Berechtigungen aus `CTokenPrivileges`\-Objekt.|  
|[CTokenPrivileges::GetCount](../Topic/CTokenPrivileges::GetCount.md)|Gibt die Anzahl der Rechteinträgen im `CTokenPrivileges`\-Objekt zurück.|  
|[CTokenPrivileges::GetDisplayNames](../Topic/CTokenPrivileges::GetDisplayNames.md)|Ruft Anzeigenamen für die Rechte ab, die im `CTokenPrivileges`\-Objekt enthalten sind.|  
|[CTokenPrivileges::GetLength](../Topic/CTokenPrivileges::GetLength.md)|Gibt die Puffergröße in Bytes erforderlich, um die **TOKEN\_PRIVILEGES**\-Struktur enthält dargestellt durch das `CTokenPrivileges`\-Objekt zurück.|  
|[CTokenPrivileges::GetLuidsAndAttributes](../Topic/CTokenPrivileges::GetLuidsAndAttributes.md)|Ruft die lokal eindeutigen Bezeichner \(LUIDs\) und die Attributflags vom `CTokenPrivileges`\-Objekt ab.|  
|[CTokenPrivileges::GetNamesAndAttributes](../Topic/CTokenPrivileges::GetNamesAndAttributes.md)|Ruft die Rechtname\- und \-Attributflags vom `CTokenPrivileges`\-Objekt ab.|  
|[CTokenPrivileges::GetPTOKEN\_PRIVILEGES](../Topic/CTokenPrivileges::GetPTOKEN_PRIVILEGES.md)|Gibt einen Zeiger auf die **TOKEN\_PRIVILEGES**\-Struktur zurück.|  
|[CTokenPrivileges::LookupPrivilege](../Topic/CTokenPrivileges::LookupPrivilege.md)|Ruft das Attribut ab, das mit einem angegebenen Rechtnamen zugeordnet ist.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTokenPrivileges::operator const TOKEN\_PRIVILEGES \*](../Topic/CTokenPrivileges::operator%20const%20TOKEN_PRIVILEGES%20*.md)|Wandelt einen Wert in einen Zeiger auf eine Struktur **TOKEN\_PRIVILEGES** um.|  
|[CTokenPrivileges::operator \=](../Topic/CTokenPrivileges::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und wird zu jedem Benutzer zugeordnet, der auf ein Windows NT\- oder Windows 2000system protokolliert wird.  
  
 Das Zugriffstoken wird verwendet, um die verschiedenen Sicherheitsberechtigungen zu beschreiben, die jedem Benutzer gewährt werden.  Ein rechts besteht aus einer 64\-Bit\-Zahl, die lokal einen eindeutigen Bezeichner \([LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)\) aufgerufen wird und eine Deskriptorzeichenfolge.  
  
 Die `CTokenPrivileges`\-Klasse ist ein Wrapper für die [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)\-Struktur und enthält 0 oder mehr Rechte.  Berechtigungen können mithilfe der angegebenen Klassenmethoden hinzugefügt, gelöscht oder abgefragt werden.  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [Beispiel für die Sicherheit](../../top/visual-cpp-samples.md)   
 [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID\_AND\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)