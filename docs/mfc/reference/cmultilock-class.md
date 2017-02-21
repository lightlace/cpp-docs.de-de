---
title: "CMultiLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiLock class"
  - "synchronization objects, Zugriffssteuerung"
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMultiLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.  
  
## Syntax  
  
```  
class CMultiLock  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](../Topic/CMultiLock::CMultiLock.md)|Erstellt ein `CMultiLock`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMultiLock::IsLocked](../Topic/CMultiLock::IsLocked.md)|Bestimmt, ob ein bestimmtes Synchronisierungsobjekt im Array gesperrt ist.|  
|[CMultiLock::Lock](../Topic/CMultiLock::Lock.md)|wartet auf dem Array von Synchronisierungsobjekten.|  
|[CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)|Gibt alle zugehörigen Synchronisierungsobjekte frei.|  
  
## Hinweise  
 `CMultiLock` hat keine Basisklasse.  
  
 Um die Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md) zu verwenden, [CMutex](../../mfc/reference/cmutex-class.md) und [CEvent](../../mfc/reference/cevent-class.md), können Sie entweder ein **CMultiLock**  oder [CSingleLock](../../mfc/reference/csinglelock-class.md)\-Objekt von Wait an erstellen und das Synchronisierungsobjekt freigeben.  Verwenden Sie **CMultiLock** , wenn mehrere Objekte gibt, die Sie zu einem bestimmten Zeitpunkt verwenden können.  Verwenden Sie `CSingleLock`, wenn Sie nur auf ein Objekt gleichzeitig warten müssen.  
  
 Um ein **CMultiLock** \-Objekt zu verwenden, erstellen Sie zuerst ein Array der Synchronisierungsobjekte warten möchten Sie die auf.  Rufen Sie anschließend den Konstruktor des **CMultiLock** \-Objekts innerhalb einer Memberfunktion in der gesteuerten Klasse der Ressource auf.  Rufen Sie dann die [Sperre](../Topic/CMultiLock::Lock.md)\-Memberfunktion auf, um zu bestimmen, ob eine Ressource verfügbar ist \(signalisiert\).  Wenn Sie, fahren Sie mit dem Rest der Memberfunktion fort.  Wenn keine Ressource, entweder verfügbar ist, warten Sie auf eine bestimmte Zeit, damit eine Ressource freigegeben werden kann, oder geben Sie Fehler zurück.  Nachgebrauch einer Ressource ist, jeder Aufruf die [Entsperren Sie](../Topic/CMultiLock::Unlock.md)\-Funktion, wenn das **CMultiLock** \-Objekt erneut verwendet werden soll, oder ermöglicht das zerstört werden **CMultiLock**  vollständig Objekt.  
  
 **CMultiLock** \-Objekte sind besonders hilfreich, wenn ein Thread große `CEvent`\-Objekte verfügt, die er auf reagieren kann.  Erstellen Sie ein Array, das alle `CEvent` Zeiger enthält, und rufen Sie `Lock` auf.  Dadurch wird der Thread zu warten, bis eines der Ereignisse signalisiert wird.  
  
 Weitere Informationen dazu, wie **CMultiLock** \-Objekte, finden Sie im Artikel [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md) verwendet.  
  
## Vererbungshierarchie  
 `CMultiLock`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)