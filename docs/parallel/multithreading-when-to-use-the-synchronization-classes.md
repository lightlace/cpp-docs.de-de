---
title: 'Multithreading: Wenn der Synchronisierungsklassen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b72b3ffac2c4c295aa997e43e52b0bf5e67fe985
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-when-to-use-the-synchronization-classes"></a>Multithreading: Verwendungsmöglichkeiten der Synchronisierungsklassen
Multithreading mit MFC bereitgestellten Klassen können zwei Kategorien zugeordnet: Synchronisierungsobjekte ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ CCriticalSection](../mfc/reference/ccriticalsection-class.md), und [CEvent](../mfc/reference/cevent-class.md)) und den Zugriff von Synchronisierungsobjekten ([CMultiLock](../mfc/reference/cmultilock-class.md) und [CSingleLock](../mfc/reference/csinglelock-class.md)).  
  
 Synchronisierungsklassen werden beim Zugriff auf eine Ressource gesteuert werden muss, um sicherzustellen, dass die Integrität der Ressource verwendet. Synchronisierungszugriffsklassen werden verwendet, um Zugriff auf diese gesteuerten Ressourcen zu erhalten. Dieses Thema beschreibt die Verwendung jeder Klasse.  
  
 Um zu bestimmen, welche Synchronisierungsklasse zu verwendende, Fragen Sie die folgende Reihe von Fragen:  
  
1.  Verfügt die Anwendung über warten, dass etwas geschehen, bevor sie die Ressource zugreifen kann (z. B. Daten empfangen werden müssen von einem Kommunikationsanschluss, bevor er in eine Datei geschrieben werden kann)?  
  
     Wenn Ja, verwenden Sie `CEvent`.  
  
2.  Kann mehrere Threads innerhalb der gleichen Anwendungszugriff dieser Ressource gleichzeitig (z. B. für Ihre Anwendung kann bis zu fünf Windows mit Sichten des gleichen Dokuments)?  
  
     Wenn Ja, verwenden Sie `CSemaphore`.  
  
3.  Kann mehr als einer Anwendung verwenden Sie diese Ressource (z. B. die Ressource wird in eine DLL-Datei)?  
  
     Wenn Ja, verwenden Sie `CMutex`.  
  
     Wenn Nein, verwenden Sie `CCriticalSection`.  
  
 **CSyncObject** wird nie direkt verwendet. Es ist die Basisklasse für die anderen vier Synchronisierungsklassen zum Einsatz.  
  
## <a name="example-1-using-three-synchronization-classes"></a>Beispiel 1: Verwenden von drei Synchronisierungsklassen  
 Als Beispiel wird eine Anwendung verwendet, in der eine verknüpfte Liste von Konten verwaltet wird. In dieser Anwendung können drei Konten in verschiedenen Fenstern untersucht werden, es kann jedoch nur jeweils ein Konto aktualisiert werden. Bei der Aktualisierung eines Kontos werden die aktualisierten Daten über das Netzwerk an ein Datenarchiv gesendet.  
  
 In dieser Beispielanwendung kommen alle drei Arten von Synchronisierungsklassen zum Einsatz. Da bis zu drei Konten gleichzeitig untersucht werden können, verwendet er `CSemaphore` Zugriff auf drei Ansichtsobjekte beschränkt. Beim Versuch, ein viertes Konto anzuzeigen, wartet die Anwendung entweder, bis eines der ersten drei Fenster geschlossen wird, oder der Versuch schlägt fehl. Wenn ein Konto aktualisiert wird, verwendet die Anwendung `CCriticalSection` , stellen Sie sicher, dass nur ein Konto zu einem Zeitpunkt aktualisiert wird. Nach erfolgreicher Aktualisierung signalisiert `CEvent`, die einen Thread wartet auf das Ereignis signalisiert werden frei. Dieser Thread sendet die neuen Daten an das Datenarchiv.  
  
## <a name="example-2-using-synchronization-access-classes"></a>Beispiel 2: Verwenden von Synchronisierungszugriffsklassen  
 Auswählen, welche Synchronisierungsklasse-Zugriff verwenden jetzt noch einfacher wird. Falls Ihre Anwendung mit nur eine einzelne gesteuerte Ressource zugreifen, verwenden Sie `CSingleLock`. Verwenden Sie bei Bedarf den Zugriff auf eine Anzahl von Ressourcen gesteuerte `CMultiLock`. In Beispiel 1 `CSingleLock` wurde verwendet hätten, da die in jedem Fall nur eine Ressource zu einem bestimmten Zeitpunkt erforderlich ist.  
  
 Informationen zur Verwendung finden Sie unter [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../parallel/multithreading-how-to-use-the-synchronization-classes.md). Weitere Informationen zur Synchronisierung finden Sie unter [Synchronisierung](http://msdn.microsoft.com/library/windows/desktop/ms686353) in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Informationen über die Multithreadunterstützung in MFC finden Sie unter [Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md)