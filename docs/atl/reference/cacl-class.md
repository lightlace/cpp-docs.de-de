---
title: "CAcl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAcl"
  - "ATL::CAcl"
  - "ATLSECURITY/CAcl"
  - "ATL.CAcl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAcl class"
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAcl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für eine Struktur `ACL` \(Access Control List\).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CAcl  
  
```  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](../Topic/CAcl::CAccessMaskArray.md)|Ein Array von `ACCESS_MASK` S.|  
|[CAcl::CAceFlagArray](../Topic/CAcl::CAceFlagArray.md)|Ein Array von `BYTE` S.|  
|[CAcl::CAceTypeArray](../Topic/CAcl::CAceTypeArray.md)|Ein Array von `BYTE` S.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAcl::CAcl](../Topic/CAcl::CAcl.md)|Der \-Konstruktor.|  
|[CAcl::~CAcl](../Topic/CAcl::~CAcl.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAcl::GetAceCount](../Topic/CAcl::GetAceCount.md)|Gibt die Anzahl von Objekten des Zugriffssteuerungseintrags \(ACE\) zurück.|  
|[CAcl::GetAclEntries](../Topic/CAcl::GetAclEntries.md)|Ruft die Einträge der Zugriffssteuerungsliste \(ACL\) vom `CAcl`\-Objekt ab.|  
|[CAcl::GetAclEntry](../Topic/CAcl::GetAclEntry.md)|Ruft alle Informationen über einen Eintrag in einem `CAcl`\-Objekt ab.|  
|[CAcl::GetLength](../Topic/CAcl::GetLength.md)|Gibt die Länge des ACLs zurück.|  
|[CAcl::GetPACL](../Topic/CAcl::GetPACL.md)|Gibt ein PACL zurück \(Zeiger auf einen ACLs\).|  
|[CAcl::IsEmpty](../Topic/CAcl::IsEmpty.md)|Testet das `CAcl`\-Objekt für Einträge.|  
|[CAcl::IsNull](../Topic/CAcl::IsNull.md)|Gibt den Status des `CAcl`\-Objekts zurück.|  
|[CAcl::RemoveAce](../Topic/CAcl::RemoveAce.md)|Entfernt bestimmtes ACE \(Zugriffssteuerungseintrag\) vom `CAcl`\-Objekt.|  
|[CAcl::RemoveAces](../Topic/CAcl::RemoveAces.md)|Entfernt alle Einträge für die Zugriffssteuerung \(ACEs\) von `CAcl`, die auf angegebene `CSid` gelten.|  
|[CAcl::SetEmpty](../Topic/CAcl::SetEmpty.md)|Markiert das Objekt, z `CAcl` leer.|  
|[CAcl::SetNull](../Topic/CAcl::SetNull.md)|Markiert das Objekt `CAcl` als `NULL`.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAcl::operator const ACL \*](../Topic/CAcl::operator%20const%20ACL%20*.md)|Wandelt ein `CAcl`\-Objekt einer `ACL`\-Struktur um.|  
|[CAcl::operator \=](../Topic/CAcl::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 Die **ACL**\-Struktur ist der Header eines ACL \(Access Control List\).  Ein ACLs enthält eine sequenzielle Liste Null ein oder mehr [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868) \(Zugriffssteuerungseinträgen\).  Die einzelnen ACEs in einem ACLs werden zwischen 0 und *n\-1* nummeriert, wobei *n* die Anzahl von ACEs im ACLs ist.  Wenn sie ein ACLs bearbeitet, verweist auf eine Anwendung einen Eintrag für die Zugriffssteuerung \(ACE\) innerhalb des ACLs durch den Index an.  
  
 Es gibt zwei ACL\-Typen:  
  
-   Bedingt  
  
-   System  
  
 Eine besitzerverwaltete ACLs wird vom Besitzer eines Objekts gesteuert, oder jedem **WRITE\_DAC** gewährte Zugriff auf das Objekt.  Sie gibt die bestimmten Benutzer des Zugriffs an und Gruppen können müssen ein Objekt.  Beispielsweise kann der Besitzer einer Datei eine besitzerverwaltete ACLs verwenden, um zu steuern, der Benutzer und Gruppen Zugriff auf die Datei aufweisen können.  
  
 Ein Objekt kann auch über die Sicherheitsinformationen auf Systemebene, die mit ihm, in Form eines Systems zugeordnet werden ACLs, das von einem Systemadministrator gesteuert wird.  Ein System ACLs können dem Systemadministrator ermöglichen, alle Versuche zu überwachen, zu einem Objekt zu erhalten.  
  
 Ausführliche Informationen finden Sie in der [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872) Diskussion in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)