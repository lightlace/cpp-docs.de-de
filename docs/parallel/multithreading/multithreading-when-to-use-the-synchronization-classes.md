---
title: "Multithreading: Verwendungsm&#246;glichkeiten der Synchronisierungsklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriff auf gesteuerte Ressource [C++]"
  - "Multithreading [C++], Synchronisierungsklassen"
  - "Ressourcen [C++], Multithreading"
  - "Synchronisierung [C++], Multithreading"
  - "Synchronisierungszugriffsklassen [C++]"
  - "Synchronisierungsklassen [C++]"
  - "Threading [C++], Synchronisierung"
  - "Threading [MFC], Synchronisierungsklassen"
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading: Verwendungsm&#246;glichkeiten der Synchronisierungsklassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die sechs in MFC enthaltenen Multithreadklassen fallen in zwei Kategorien: Synchronisierungsobjekte \([CSyncObject](../../mfc/reference/csyncobject-class.md), [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md) sowie [CEvent](../../mfc/reference/cevent-class.md)\) und Synchronisierungszugriffsobjekte \([CMultiLock](../../mfc/reference/cmultilock-class.md) sowie [CSingleLock](../../mfc/reference/csinglelock-class.md)\).  
  
 Synchronisierungsklassen kommen zum Einsatz, wenn der Zugriff auf eine Ressource gesteuert werden muss, um die Integrität der Ressource sicherzustellen.  Synchronisierungszugriffsklassen ermöglichen den Zugriff auf diese gesteuerten Ressourcen.  In diesem Thema erfahren Sie, in welchen Fällen die einzelnen Klassen verwendet werden.  
  
 Zur Ermittlung der zu verwendenden Synchronisierungsklasse müssen folgende Punkte geklärt werden:  
  
1.  Muss die Anwendung auf einen bestimmten Vorgang warten, bevor sie auf die Ressource zugreifen kann \(müssen z. B. Daten von einem Kommunikationsanschluss übertragen werden, bevor sie in eine Datei geschrieben werden können\)?  
  
     Verwenden Sie `CEvent`, wenn dies der Fall ist.  
  
2.  Können mehrere Threads innerhalb derselben Anwendung gleichzeitig auf diese Ressource zugreifen \(können in einer Anwendung z. B. bis zu fünf Fenster mit Ansichten desselben Dokuments angezeigt werden\)?  
  
     Verwenden Sie `CSemaphore`, wenn dies der Fall ist.  
  
3.  Können mehrere Anwendungen diese Ressource verwenden \(befindet sich die Ressource z. B. in einer DLL\)?  
  
     Verwenden Sie `CMutex`, wenn dies der Fall ist.  
  
     Verwenden Sie `CCriticalSection`, wenn dies nicht der Fall ist.  
  
 **CSyncObject** wird nie direkt verwendet.  Es handelt es sich hierbei um die Basisklasse für die anderen vier Synchronisierungsklassen.  
  
## Beispiel 1: Verwenden von drei Synchronisierungsklassen  
 Als Beispiel wird eine Anwendung verwendet, in der eine verknüpfte Liste von Konten verwaltet wird.  In dieser Anwendung können drei Konten in verschiedenen Fenstern untersucht werden, es kann jedoch nur jeweils ein Konto aktualisiert werden.  Bei der Aktualisierung eines Kontos werden die aktualisierten Daten über das Netzwerk an ein Datenarchiv gesendet.  
  
 In dieser Beispielanwendung kommen alle drei Arten von Synchronisierungsklassen zum Einsatz.  Da bis zu drei Konten gleichzeitig untersucht werden können, wird mithilfe von `CSemaphore` der Zugriff auf drei Ansichtsobjekte beschränkt.  Beim Versuch, ein viertes Konto anzuzeigen, wartet die Anwendung entweder, bis eines der ersten drei Fenster geschlossen wird, oder der Versuch schlägt fehl.  Bei der Aktualisierung eines Kontos verwendet die Anwendung `CCriticalSection`, um sicherzustellen, dass nur jeweils ein Konto aktualisiert wird.  Nach erfolgreicher Aktualisierung signalisiert sie `CEvent`, die einen Thread freigibt, der auf die Signalisierung des Ereignisses wartet.  Dieser Thread sendet die neuen Daten an das Datenarchiv.  
  
## Beispiel 2: Verwenden von Synchronisierungszugriffsklassen  
 Die Wahl der zu verwendenden Synchronisierungszugriffsklasse gestaltet sich noch deutlich problemloser.  Falls eine Anwendung nur auf eine einzelne gesteuerte Ressource zugreift, verwenden Sie `CSingleLock`.  Falls sie jedoch auf eine von mehreren gesteuerten Ressourcen zugreifen muss, verwenden Sie `CMultiLock`.  In Beispiel 1 wäre `CSingleLock` zum Einsatz gekommen, da in jedem Fall nur eine Ressource zu einem bestimmten Zeitpunkt benötigt wird.  
  
 Informationen zur Verwendung von Synchronisierungsklassen finden Sie unter [Multithreading: Verwendungsweise der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  Weitere Informationen über Synchronisierung finden Sie im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] unter [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353).  Weitere Informationen über die Multithreadunterstützung in MFC finden Sie unter [Multithreading mit C\+\+ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md).  
  
## Siehe auch  
 [Multithreading mit C\+\+ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md)