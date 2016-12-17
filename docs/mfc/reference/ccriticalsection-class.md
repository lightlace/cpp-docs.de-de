---
title: "CCriticalSection Class"
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
  - "CCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCriticalSection class"
  - "critical sections"
  - "Synchronisierungsklassen, CCriticalSection class"
  - "synchronization objects, critical section"
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen "kritischen Abschnitt" dar \- ein Synchronisierungsobjekt, das einen Thread auf einmal ermöglicht, eine Ressource oder einen Codeabschnitt zuzugreifen.  
  
## Syntax  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](../Topic/CCriticalSection::CCriticalSection.md)|Erstellt ein `CCriticalSection`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCriticalSection::Lock](../Topic/CCriticalSection::Lock.md)|Verwenden Sie, um `CCriticalSection`\-Objekt zu erhalten.|  
|[CCriticalSection::Unlock](../Topic/CCriticalSection::Unlock.md)|Gibt das `CCriticalSection`\-Objekt frei.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL\_SECTION\*](../Topic/CCriticalSection::operator%20CRITICAL_SECTION*.md)|Ruft einen Zeiger auf den internen **CRITICAL\_SECTION**\-Objekt ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CCriticalSection::m\_sect](../Topic/CCriticalSection::m_sect.md)|Ein **CRITICAL\_SECTION**\-Objekt.|  
  
## Hinweise  
 Kritische Abschnitte sind nützlich, wenn nur einen Thread auf einmal ermöglicht werden kann, um Daten oder eine andere gesteuerte Ressource zu ändern.  Beispielsweise Knoten zu einer verknüpften Liste hinzuzufügen ist ein Prozess, der durch einen Thread nur jeweils ausgeführt werden dürfen.  Durch ein `CCriticalSection`\-Objekt verwendet, um die verknüpfte Liste zu steuern, kann nur ein Thread zur Liste auf einmal verschaffen.  
  
> [!NOTE]
>  Die Funktionalität der `CCriticalSection`\-Klasse wurde von einem tatsächlichen Objekt Win32 **CRITICAL\_SECTION** bereitgestellt.  
  
 Kritische Abschnitte werden anstelle der Mutexe verwendet \(siehe [CMutex](../../mfc/reference/cmutex-class.md)\), wenn Geschwindigkeit wichtig ist und die Ressource nicht über Prozessgrenzen verwendet wird.  
  
 Es gibt zwei Methoden für die Anwendung eines `CCriticalSection`\-Objekts: eigenständig und in einer Klasse eingebettet.  
  
-   Die eigenständige Methode, um einen eigenständigen `CCriticalSection`\-Objekts zu verwenden, erstellen das Objekt `CCriticalSection`, wenn sie benötigt wird.  Nachdem eine erfolgreiche Rückgabe aus dem Konstruktor, explizit das Objekt mit einem Aufruf von [Sperre](../Topic/CCriticalSection::Lock.md) sperren.  Rufen Sie [Entsperren Sie](../Topic/CCriticalSection::Unlock.md) auf, wenn Sie auf den kritischen Abschnitt Dateizugriff durchgeführt werden.  Diese Methode, während klarer an jemanden, das den Quellcode lesen, ist fehleranfälliger, wie Sie wissen müssen, den kritischen Abschnitt vor und nach Zugriff zu sperren und zu entsperren.  
  
     Eine vorzuziehendere Methode ist, die [CSingleLock](../../mfc/reference/csinglelock-class.md)\-Klasse zu verwenden.  Sie enthält außerdem eine `Lock` und `Unlock`\-Methode, müssen aber nicht um das Entsperren der Ressource zu befürchten, wenn eine Ausnahme auftritt.  
  
-   Eingebettete Methode können Sie eine Klasse mit mehreren Threads freigeben, indem Sie bei Bedarf einen en\-artig Datenmember `CCriticalSection` hinzufügen und Datenmember sperren.  
  
 Weitere Informationen zur Verwendung von `CCriticalSection`\-Objekten, finden Sie im Artikel [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMutex Class](../../mfc/reference/cmutex-class.md)