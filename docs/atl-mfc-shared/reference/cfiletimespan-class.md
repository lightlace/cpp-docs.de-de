---
title: "CFileTimeSpan Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CFileTimeSpan"
  - "ATL.CFileTimeSpan"
  - "ATL::CFileTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTimeSpan class"
  - "shared classes, CFileTimeSpan"
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CFileTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Verwalten von den relativen Datums\- und Uhrzeitwerte bereit, die einer Datei zugeordnet werden.  
  
## Syntax  
  
```  
  
class CFileTimeSpan  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](../Topic/CFileTimeSpan::CFileTimeSpan.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](../Topic/CFileTimeSpan::GetTimeSpan.md)|Rufen Sie diese Methode auf, um die Zeitspanne `CFileTimeSpan` vom Objekt abzurufen.|  
|[CFileTimeSpan::SetTimeSpan](../Topic/CFileTimeSpan::SetTimeSpan.md)|Rufen Sie diese Methode auf, um die Dauer des `CFileTimeSpan`\-Objekts festzulegen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTimeSpan::operator \-](../Topic/CFileTimeSpan::operator%20-.md)|Führt Subtraktion auf einem `CFileTimeSpan`\-Objekt.|  
|[CFileTimeSpan::operator \!\=](../Topic/CFileTimeSpan::operator%20!=.md)|Überprüft zwei `CFileTimeSpan`\-Objekte auf Ungleichheit.|  
|[CFileTimeSpan::operator \+](../Topic/CFileTimeSpan::operator%20+.md)|Führt Addition auf einem `CFileTimeSpan`\-Objekt.|  
|[CFileTimeSpan::operator \+\=](../Topic/CFileTimeSpan::operator%20+=.md)|Führt Addition auf einem `CFileTimeSpan`\-Objekt aus und weist das Ergebnis dem aktuellen Objekt zu.|  
|[CFileTimeSpan::operator \<](../Topic/CFileTimeSpan::operator%20%3C.md)|Vergleicht zwei `CFileTimeSpan`\-Objekte, um die kleiner zu bestimmen.|  
|[CFileTimeSpan::operator \<\=](../Topic/CFileTimeSpan::operator%20%3C=.md)|Vergleicht zwei `CFileTimeSpan`\-Objekte, um die Gleichheit oder kleiner zu bestimmen.|  
|[CFileTimeSpan::operator \=](../Topic/CFileTimeSpan::operator%20=.md)|Der Zuweisungsoperator.|  
|[CFileTimeSpan::operator \-\=](../Topic/CFileTimeSpan::operator%20-=.md)|Führt Subtraktion auf einem `CFileTimeSpan`\-Objekt aus und weist das Ergebnis dem aktuellen Objekt zu.|  
|[CFileTimeSpan::operator \=\=](../Topic/CFileTimeSpan::operator%20==.md)|Überprüft zwei `CFileTimeSpan`\-Objekte auf Gleichheit.|  
|[CFileTimeSpan::operator \>](../Topic/CFileTimeSpan::operator%20%3E.md)|Vergleicht zwei `CFileTimeSpan`\-Objekte, um das größere zu bestimmen.|  
|[CFileTimeSpan::operator \>\=](../Topic/CFileTimeSpan::operator%20%3E=.md)|Vergleicht zwei `CFileTimeSpan`\-Objekte, um Gleichheit oder das größere zu bestimmen.|  
  
## Hinweise  
 Diese Klasse stellt Methoden zum Verwalten von den relativen Zeiträumen bereit, die häufig beim Vorgänge hinsichtlich auftreten, ausgeführt wird, als eine Datei erstellt wurde, zuletzt verwendet oder Auslastung aufgenommen werden.  Die Methoden dieser Klasse werden häufig in Verbindung mit [CFileTime\-Klasse](../../atl-mfc-shared/reference/cfiletime-class.md)\-Objekte.  
  
## Beispiel  
 Im Beispiel für [CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md).  
  
## Anforderungen  
 **Header:** atltime.h  
  
## Siehe auch  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime Class](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)