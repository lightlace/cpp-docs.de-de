---
title: "Strukturen für Synchronisierungsdaten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1dd1c47cad01e0324f8027593eb4933f70cd6191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="synchronization-data-structures"></a>Synchronisierungsdatenstrukturen
Die Concurrency Runtime bietet verschiedene Datenstrukturen, mit denen Sie Zugriff auf freigegebene Daten von mehreren Threads synchronisiert. Diese Datenstrukturen sind nützlich, wenn Sie Daten freigegeben haben, die selten geändert werden. Ein Synchronisierungsobjekt, z. B. einen kritischen Abschnitt führt dazu, dass andere Threads zu warten, bis die freigegebene Ressource verfügbar ist. Wenn Sie ein solches Objekt verwenden, um den Zugriff auf Daten zu synchronisieren, die häufig verwendet wird, können Sie Skalierbarkeit in Ihrer Anwendung verlieren. Die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) bietet die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse, die Sie zum Freigeben einer Ressource auf mehrere Threads oder Aufgaben ohne die Notwendigkeit einer Synchronisierung ermöglicht. Weitere Informationen zu den `combinable` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="top"></a> Abschnitte  
 In diesem Thema werden die folgenden asynchronen Nachrichtenblocktypen im Detail beschrieben:  
  
-   [critical_section](#critical_section)  
  
-   [reader_writer_lock](#reader_writer_lock)  
  
-   [Scoped_lock und scoped_lock_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a>critical_section  
 Die [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) Klasse stellt ein kooperativen gegenseitige Ausschlussobjekt, die zu anderen Aufgaben statt zu vermeiden, diese ergibt. Kritische Abschnitte sind nützlich, wenn mehrere Threads auf exklusiven Lese- und Schreibzugriff auf freigegebene Daten benötigen.  

 Die `critical_section` Klasse ist nicht wiedereintretend. Die [Concurrency::critical_section::lock](reference/critical-section-class.md#lock) Methode löst eine Ausnahme vom Typ [Concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) , wenn sie vom Thread aufgerufen wird, die bereits im Besitz der Sperre.  


  
### <a name="methods-and-features"></a>Methoden und Funktionen  
 Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `critical_section` Klasse.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[lock](reference/critical-section-class.md#lock)|Ruft den kritischen Abschnitt ab. Der aufrufenden Kontext blockiert, bis er die Sperre erhält.|  
|[try_lock](reference/critical-section-class.md#try_lock)|Den kritischen Abschnitt zu erhalten versucht, jedoch nicht blockiert.|  
|[unlock](reference/critical-section-class.md#unlock)|Gibt den kritischen Abschnitt frei.|  
  
 [[Nach oben](#top)]  
  
##  <a name="reader_writer_lock"></a>reader_writer_lock  
 Die [Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) -Klasse stellt threadsichere Lese-/Schreibvorgänge auf freigegebene Daten. Verwenden Sie Lese-/Schreibsperren, wenn mehrere Threads gleichzeitig Lesezugriff auf eine freigegebene Ressource erfordern jedoch selten auf die freigegebene Ressource schreiben. Diese Klasse bietet nur einen Thread Schreibzugriff auf ein Objekt zu einem beliebigen Zeitpunkt.  
  
 Die `reader_writer_lock` Klasse ausführen kann besser als die `critical_section` Klasse, da ein `critical_section` -Objekt abruft, exklusiven Zugriff auf eine freigegebene Ressource, wird verhindert, dass gleichzeitige Lesezugriff.  
  
 Wie die `critical_section` -Klasse, die `reader_writer_lock` Klasse stellt ein kooperativen gegenseitige Ausschlussobjekt, die zu anderen Aufgaben statt zu vermeiden, diese ergibt.  
  
 Wenn ein Thread, der auf eine freigegebene Ressource schreiben muss, eine Lese-/Schreibsperre abruft, werden die anderen Threads, die auch Zugriff auf die Ressource müssen blockiert, bis der Writer die Sperre frei. Die `reader_writer_lock` Klasse ist ein Beispiel für eine *"Write-preference"* Sperre, die eine Sperre, die wartende Writer Blockierung aufgehoben wird handelt, bevor wartende Leser Blockierung aufgehoben wird.  
  
 Wie die `critical_section` -Klasse, die `reader_writer_lock` Klasse ist nicht wiedereintretend. Die [Concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock) und [Concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read) Methoden lösen eine Ausnahme vom Typ `improper_lock` , wenn sie von einem Thread aufgerufen werden, die bereits im Besitz die Sperre.  


  
> [!NOTE]
>  Da die `reader_writer_lock` Klasse ist nicht wieder eintretender, können Sie ein upgrade eine nur-Lese Sperre auf eine Lese-/Schreibsperre oder downgrade einer Sperrung Leser/Schreibersperre an eine nur-Lese Sperre. Ausführen einer dieser Vorgänge erzeugt nicht definiertes Verhalten.  
  
### <a name="methods-and-features"></a>Methoden und Funktionen  
 Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `reader_writer_lock` Klasse.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[lock](reference/reader-writer-lock-class.md#lock)|Ruft die Lese-/Schreibzugriff auf die Sperre ab.|  
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Lese-/Schreibzugriff auf die Sperre zu erhalten versucht, jedoch nicht blockiert.|  
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Ruft schreibgeschützten Zugriff auf die Sperre ab.|  
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Nur-Lese Zugriff auf die Sperre zu erhalten versucht, jedoch nicht blockiert.|  
|[unlock](reference/reader-writer-lock-class.md#unlock)|Hebt die Sperre.|  
  
 [[Nach oben](#top)]  
  
##  <a name="scoped_lock"></a>Scoped_lock und scoped_lock_read  
 Die `critical_section` und `reader_writer_lock` Klassen bieten geschachtelte Hilfsklassen, die vereinfachen, wie Sie mit gegenseitigen Ausschluss-Objekten arbeiten. Diese Hilfsklassen werden als bezeichnet *bewertete Sperren*.  
  
 Die `critical_section` Klasse enthält die [Concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) Klasse. Der Konstruktor erhält Zugriff auf das bereitgestellte `critical_section` Objekt, und der Destruktor gibt Versionen den Zugriff auf dieses Objekt. Die `reader_writer_lock` Klasse enthält die [Concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) -Klasse, die ähnelnde `critical_section::scoped_lock`, außer dass er über Schreibzugriff auf das bereitgestellte verwaltet `reader_writer_lock` Objekt. Die `reader_writer_lock` Klasse enthält auch die [Concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) Klasse. Diese Klasse verwaltet den Lesezugriff auf das bereitgestellte `reader_writer_lock` Objekt.  

  
 Bewertete Sperren bietet einige Vorteile bei der Arbeit mit `critical_section` und `reader_writer_lock` Objekte manuell. In der Regel können Sie eine bewertete Sperre auf dem Stapel zuweisen. Eine bewertete Sperre den Zugriff auf das gegenseitige Ausschlussobjekt automatisch freigibt, wenn es zerstört wird; aus diesem Grund wird das zugrunde liegende Objekt nicht manuell entsperrt. Dies ist nützlich, wenn eine Funktion mehrere enthält `return` Anweisungen. Bewertete Sperren hilft Ihnen das Schreiben von ausnahmesicherem Code auch. Wenn eine `throw` Anweisung bewirkt, dass Entladen des Stapels, der Destruktor für eine beliebige aktive bewertete Sperre aufgerufen wird und daher das gegenseitige Ausschlussobjekt immer ordnungsgemäß freigegeben ist.  
  
> [!NOTE]
>  Bei Verwendung der `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, und `reader_writer_lock::scoped_lock_read` Klassen nicht manuell den Zugriff auf die zugrunde liegende gegenseitige Ausschlussobjekt freigegeben. Dadurch kann die Laufzeit in einem ungültigen Zustand versetzt werden.  
  
##  <a name="event"></a>Ereignis  
 Die [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) Klasse stellt ein Synchronisierungsobjekt, deren Zustand signalisiert oder nicht signalisiert werden kann. Im Gegensatz zu Synchronisierungsobjekten, z. B. kritische Abschnitte, die, die dazu dient, um Zugriff auf freigegebene Daten zu schützen, synchronisieren Ereignisse Fluss der Ausführung.  
  
 Die `event` Klasse ist hilfreich, wenn eine Aufgabe Arbeitsaufgaben für eine andere Aufgabe abgeschlossen wurde. Eine Aufgabe kann eine andere Aufgabe z. B. darauf hinweisen, dass sie Daten über eine Netzwerkverbindung oder aus einer Datei gelesen hat.  
  
### <a name="methods-and-features"></a>Methoden und Funktionen  
 Die folgende Tabelle zeigt einige wichtige Methoden, die von definiert sind die `event` Klasse.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Warte](reference/event-class.md#wait)|Wartet, bis das Ereignis signalisiert wird.|  
|[set](reference/event-class.md#set)|Legt das Ereignis auf den Zustand "signalisiert" fest.|  
|[reset](reference/event-class.md#reset)|Legt das Ereignis in den nicht signalisierten Zustand fest.|  
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Wartet, bis mehrere Ereignisse signalisiert werden.|  

  
### <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung der `event` Klasse, finden Sie unter [Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 [[Nach oben](#top)]  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Wird das Verhalten von der Windows-API bereitgestellten Synchronisierungsdatenstrukturen verglichen.  
  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)  
 Beschreibt die Concurrency Runtime, die die parallele Programmierung vereinfacht, und stellt Links zu verwandten Themen bereit.

