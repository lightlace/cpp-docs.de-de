---
title: "CSyncObject Class"
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
  - "CSyncObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSyncObject class"
  - "Synchronisierungsklassen, CSyncObject"
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CSyncObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine reine virtuelle Klasse, die die Funktionalität zu den Synchronisierungsobjekte in Win32 bereitstellt.  
  
## Syntax  
  
```  
class CSyncObject : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](../Topic/CSyncObject::CSyncObject.md)|Erstellt ein `CSyncObject`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::Lock](../Topic/CSyncObject::Lock.md)|Ruft den Synchronisierungsobjekt zugreifen.|  
|[CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md)|Ruft den Synchronisierungsobjekt zugreifen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::operator HANDLE](../Topic/CSyncObject::operator%20HANDLE.md)|Bietet Zugriff auf den Synchronisierungsobjekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::m\_hObject](../Topic/CSyncObject::m_hObject.md)|Das Handle für den zugrunde liegenden Synchronisierungsobjekt.|  
  
## Hinweise  
 Microsoft Foundation Class\-Bibliothek stellt mehrere Klassen, die von `CSyncObject` abgeleitet werden.  Diese sind [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md) und [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Informationen dazu, wie Sie die Synchronisierungsobjekte, finden Sie im Artikel [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md) verwendet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)