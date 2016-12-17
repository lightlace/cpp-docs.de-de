---
title: "CDacl Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDacl"
  - "CDacl"
  - "ATL.CDacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDacl class"
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CDacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für eine Struktur DACL \(besitzerverwaltete Zugriffssteuerungsliste\).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CDacl : public CAcl  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDacl::CDacl](../Topic/CDacl::CDacl.md)|Der \-Konstruktor.|  
|[CDacl::~CDacl](../Topic/CDacl::~CDacl.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](../Topic/CDacl::AddAllowedAce.md)|Fügt zulässigen ACE \(Zugriffssteuerungseintrag\) dem `CDacl`\-Objekt hinzu.|  
|[CDacl::AddDeniedAce](../Topic/CDacl::AddDeniedAce.md)|Fügt verweigertes ACE dem `CDacl`\-Objekt hinzu.|  
|[CDacl::GetAceCount](../Topic/CDacl::GetAceCount.md)|Gibt die Anzahl von ACEs \(Zugriffssteuerungseinträgen\) im `CDacl`\-Objekt zurück.|  
|[CDacl::RemoveAce](../Topic/CDacl::RemoveAce.md)|Entfernt bestimmtes ACE \(Zugriffssteuerungseintrag\) vom `CDacl`\-Objekt.|  
|[CDacl::RemoveAllAces](../Topic/CDacl::RemoveAllAces.md)|Entfernt alle ACEs, die im `CDacl`\-Objekt enthalten sind.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDacl::operator \=](../Topic/CDacl::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 Die Sicherheitsbeschreibung eines Objekts kann DACL enthalten.  Ein DACLs enthalten keine oder mehrere Einträge für die Zugriffssteuerung \(ACEs\) die Benutzer und Gruppen identifizieren, die auf das Objekt zugreifen können.  Wenn DACL \(das heißt, enthält es nullasse\), leer ist, wird kein Zugriff explizit erteilt, daher wird implizit Zugriff verweigert.  Wenn die Sicherheitsbeschreibung eines Objekts kein DACL, wird das Objekt nicht geschützt und jeder vollständigen Zugriff hat.  
  
 Um die DACL eines Objekts abzurufen, müssen Sie der Besitzer des Objekts sein oder READ\_CONTROL\-Zugriff zum Objekt verfügen.  Um die DACL eines Objekts zu ändern, müssen Sie WRITE\_DAC\-Zugriff zum Objekt verfügen.  
  
 Verwenden Sie die Klassenmethoden, die bereitgestellt werden, um ACEs vom `CDacl`\-Objekt zu erstellen, hinzuzufügen, zu entfernen und zu löschen.  Siehe auch [AtlGetDacl](../Topic/AtlGetDacl.md) und [AtlSetDacl](../Topic/AtlSetDacl.md).  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [Beispiel für die Sicherheit](../../top/visual-cpp-samples.md)   
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)