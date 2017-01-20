---
title: "CSingleLock Class"
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
  - "CSingleLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleLock class"
  - "synchronization objects, Zugriffssteuerung"
  - "Threading [MFC], Zugriffssteuerung"
  - "Threading [MFC], Synchronisierung"
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CSingleLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.  
  
## Syntax  
  
```  
  
class CSingleLock  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](../Topic/CSingleLock::CSingleLock.md)|Erstellt ein `CSingleLock`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSingleLock::IsLocked](../Topic/CSingleLock::IsLocked.md)|Bestimmt, ob das Objekt gesperrt ist.|  
|[CSingleLock::Lock](../Topic/CSingleLock::Lock.md)|wartet auf einem Synchronisierungsobjekt.|  
|[CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)|Gibt ein Synchronisierungsobjekt frei.|  
  
## Hinweise  
 `CSingleLock` hat keine Basisklasse.  
  
 Um die Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md) zu verwenden, [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md) und [CEvent](../../mfc/reference/cevent-class.md), müssen Sie entweder `CSingleLock` oder [CMultiLock](../../mfc/reference/cmultilock-class.md)\-Objekt von Wait an erstellen und das Synchronisierungsobjekt freigeben.  Verwenden Sie `CSingleLock`, wenn Sie nur auf ein Objekt gleichzeitig warten müssen.  Verwenden Sie **CMultiLock** , wenn mehrere Objekte gibt, die Sie zu einem bestimmten Zeitpunkt verwenden können.  
  
 Um ein `CSingleLock`\-Objekt zu verwenden, rufen Sie ihren Konstruktor innerhalb einer Memberfunktion in der gesteuerten Klasse der Ressource auf.  Rufen Sie dann die [IsLocked](../Topic/CSingleLock::IsLocked.md)\-Memberfunktion auf, um zu bestimmen, ob die Ressource verfügbar ist.  Wenn ja, fahren Sie mit dem Rest der Memberfunktion fort.  Wenn die Ressource, entweder nicht verfügbar ist, warten Sie auf eine bestimmte Zeit, damit die Ressource freigegeben werden kann, oder geben Sie Fehler zurück.  Nachgebrauch der Ressource ist, jeder Aufruf die [Entsperren Sie](../Topic/CSingleLock::Unlock.md)\-Funktion, wenn das `CSingleLock`\-Objekt erneut verwendet werden soll, oder ermöglicht das zerstört werden `CSingleLock` vollständig Objekt.  
  
 `CSingleLock`\-Objekte benötigen das Vorhandensein eines Objekts, das von [CSyncObject](../../mfc/reference/csyncobject-class.md) abgeleitet wird.  Dies ist normalerweise ein Datenmember der gesteuerten Klasse der Ressource.  Weitere Informationen dazu, wie `CSingleLock`\-Objekte, finden Sie im Artikel [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md) verwendet.  
  
## Vererbungshierarchie  
 `CSingleLock`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMultiLock Class](../../mfc/reference/cmultilock-class.md)