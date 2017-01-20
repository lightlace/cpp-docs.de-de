---
title: "CRecentFileList Class"
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
  - "CRecentFileList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentFileList class"
  - "Dateien [C++], most recently used"
  - "MRU-Dateien"
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CRecentFileList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stützsteuerelement der zuletzt verwendeten Dateiliste \(MRU\).  
  
## Syntax  
  
```  
class CRecentFileList  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](../Topic/CRecentFileList::CRecentFileList.md)|Erstellt ein `CRecentFileList`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRecentFileList::Add](../Topic/CRecentFileList::Add.md)|Fügt eine Datei der MRU\-Dateiliste hinzu.|  
|[CRecentFileList::GetDisplayName](../Topic/CRecentFileList::GetDisplayName.md)|Gibt einen Anzeigenamen für Menüanzeige eines MRU\-Dateinamens an.|  
|[CRecentFileList::GetSize](../Topic/CRecentFileList::GetSize.md)|Ruft die Anzahl von Dateien in der MRU\-Dateiliste ab.|  
|[CRecentFileList::ReadList](../Topic/CRecentFileList::ReadList.md)|Liest die MRU\-Dateiliste aus der Registrierung oder der INI\-Datei.|  
|[CRecentFileList::Remove](../Topic/CRecentFileList::Remove.md)|Entfernt eine Datei aus der MRU\-Dateiliste.|  
|[CRecentFileList::UpdateMenu](../Topic/CRecentFileList::UpdateMenu.md)|Aktualisiert die Menüanzeige der MRU\-Dateiliste.|  
|[CRecentFileList::WriteList](../Topic/CRecentFileList::WriteList.md)|Schreibt die MRU\-Dateiliste aus der Registrierung oder der INI\-Datei.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRecentFileList::operator](../Topic/CRecentFileList::operator.md)|Gibt ein `CString`\-Objekt an einer angegebenen Position zurück.|  
  
## Hinweise  
 Dateien können hinzugefügt oder aus der MRU\-Dateiliste gelöscht werden, kann die Dateiliste von gelesen werden oder der Registrierung oder einer INI\-Datei geschrieben werden, und das Menü, das die MRU\-Dateiliste anzeigt, kann aktualisiert werden.  
  
 Weitere Informationen zu MRU\-Menüelemente, finden Sie unter  
  
-   Knowledge Base\-Artikel Q243751: HOWTO: Fügen Sie Befehlshandler für MRU\-Menüelemente in der MFC\-Anwendung hinzu  
  
## Vererbungshierarchie  
 `CRecentFileList`  
  
## Anforderungen  
 **Header:**  afxadv.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)