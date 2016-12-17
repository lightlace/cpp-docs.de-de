---
title: "CSacl Class"
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
  - "ATL.CSacl"
  - "ATL::CSacl"
  - "CSacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSacl class"
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CSacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für eine Struktur Systemzugriffssteuerungsliste \(SACL\).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CSacl : public CAcl  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSacl::CSacl](../Topic/CSacl::CSacl.md)|Der \-Konstruktor.|  
|[CSacl::~CSacl](../Topic/CSacl::~CSacl.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSacl::AddAuditAce](../Topic/CSacl::AddAuditAce.md)|Fügt einen Überwachungszugriffssteuerungseintrag \(ACE\) dem `CSacl`\-Objekt hinzu.|  
|[CSacl::GetAceCount](../Topic/CSacl::GetAceCount.md)|Gibt die Anzahl von Zugriffssteuerungseinträgen \(ACEs\) im `CSacl`\-Objekt zurück.|  
|[CSacl::RemoveAce](../Topic/CSacl::RemoveAce.md)|Entfernt bestimmtes ACE \(Zugriffssteuerungseintrag\) vom **CSacl** \-Objekt.|  
|[CSacl::RemoveAllAces](../Topic/CSacl::RemoveAllAces.md)|Entfernt alle ACEs, die im `CSacl`\-Objekt enthalten sind.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSacl::operator \=](../Topic/CSacl::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 Ein SACLs enthält Einträge für die Zugriffssteuerung \(ACEs\) die die Typen der Zugriffsversuchen angeben, die Überwachungsdatensätze im Sicherheitsereignisprotokoll eines Domänencontrollers generieren.  Beachten Sie, dass ein SACLs Protokolleinträge nur auf dem Domänencontroller, in dem der Zugriffsversuch aufgetreten ist, nicht auf jedem Domänencontroller generiert, der ein Replikat des Objekts enthält.  
  
 Um das SACLs in der Sicherheitsbeschreibung eines Objekts festzulegen oder abzurufen, muss das SE\_SECURITY\_NAME\-Recht im Zugriffstoken des anfordernden Threads aktiviert werden.  Die Administratorgruppe können dieses Recht standardmäßig gewähren, und es kann andere Benutzer oder Gruppen gewährt werden.  Das Recht gewähren lassen ist nicht ausreicht, das erforderlich ist: vor der Vorgang, der durch das Recht definiert ist, ausgeführt werden kann, muss das Recht im Sicherheitszugriffstoken aktiviert werden, um in wirksam.  Das Modell können Sie Berechtigungen, nur für bestimmte Systemoperationen aktiviert werden, und dann deaktiviert werden, wenn sie nicht mehr benötigt werden.  Siehe [AtlGetSacl](../Topic/AtlGetSacl.md) und [AtlSetSacl](../Topic/AtlSetSacl.md) für Beispiele der Aktivierung von SE\_SECURITY\_NAME.  
  
 Verwenden Sie die Klassenmethoden, die bereitgestellt werden, um ACEs vom **SACL**\-Objekt hinzuzufügen, zu entfernen, zu erstellen und zu löschen.  Siehe auch [AtlGetSacl](../Topic/AtlGetSacl.md) und [AtlSetSacl](../Topic/AtlSetSacl.md).  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)