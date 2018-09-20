---
title: Synchronisierungsdatenstrukturen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f6a57495fdd5084b3ac329f45aa816eea9274f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436194"
---
# <a name="synchronization-data-structures"></a>Synchronisierungsdatenstrukturen

Die Concurrency Runtime bietet verschiedene Datenstrukturen, mit denen Sie den Zugriff auf freigegebene Daten aus mehreren Threads zu synchronisieren. Diese Datenstrukturen sind nützlich, wenn Sie die Daten geteilt haben, die nur selten geändert werden. Ein Synchronisierungsobjekt, z. B. einen kritischen Abschnitt bewirkt, dass andere Threads warten, bis die freigegebene Ressource verfügbar ist. Wenn Sie ein solches Objekt verwenden, um den Zugriff auf Daten zu synchronisieren, die häufig verwendet wird, können Sie aus diesem Grund Skalierbarkeit in Ihrer Anwendung verlieren. Die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) bietet die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse, die Ihnen ermöglicht, eine Ressource von mehreren Threads bzw. ausführen, ohne die Notwendigkeit einer Synchronisierung freigeben. Weitere Informationen zu den `combinable` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).

##  <a name="top"></a> Abschnitte

In diesem Thema werden die folgenden asynchronen Nachrichtenblocktypen ausführlicher beschrieben:

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [Scoped_lock und scoped_lock_read](#scoped_lock)

- [event](#event)

##  <a name="critical_section"></a> critical_section

Die [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) Klasse stellt ein kooperativen gegenseitige Ausschlussobjekt, der ergibt, an andere Aufgaben statt präemptiv unterbrochen werden. Kritische Abschnitte sind nützlich, wenn mehrere Threads auf exklusiven Lese- und Schreibzugriff auf freigegebene Daten erforderlich ist.

Die `critical_section` -Klasse ist nicht wiedereintrittsfähig. Die [Concurrency::critical_section::lock](reference/critical-section-class.md#lock) Methode löst eine Ausnahme vom Typ [Concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) Wenn sie von dem Thread aufgerufen wird, die bereits im Besitz der Sperre.

### <a name="methods-and-features"></a>Methoden und Funktionen

Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `critical_section` Klasse.

|Methode|Beschreibung|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|Ruft den kritischen Abschnitt ab. Die aufrufenden Kontext blockiert, bis er die Sperre erhält.|
|[try_lock](reference/critical-section-class.md#try_lock)|Versucht, den kritischen Abschnitt anzufordern, aber nicht blockiert.|
|[unlock](reference/critical-section-class.md#unlock)|Gibt den kritischen Abschnitt frei.|

[[Nach oben](#top)]

##  <a name="reader_writer_lock"></a> reader_writer_lock

Die [Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Klasse stellt die Thread-sichere Lese/Schreib-Vorgänge auf freigegebene Daten bereit. Verwenden Sie Reader-/Writer-sperren, wenn mehrere Threads gleichzeitig der Lesezugriff auf eine freigegebene Ressource erfordern, aber nur selten auf die freigegebene Ressource schreiben. Diese Klasse bietet nur einen Thread-Schreibzugriff auf ein Objekt zu einem beliebigen Zeitpunkt.

Die `reader_writer_lock` Klasse ausgeführt werden kann besser als die `critical_section` Klasse, da eine `critical_section` -Objekt abruft, exklusiven Zugriff auf eine freigegebene Ressource, die verhindert, gleichzeitige Lesezugriff dass.

Wie die `critical_section` -Klasse, die `reader_writer_lock` Klasse stellt ein kooperativen gegenseitige Ausschlussobjekt, der ergibt, an andere Aufgaben statt präemptiv unterbrochen werden.

Wenn ein Thread, der in eine freigegebene Ressource schreiben muss, um eine Reader-/Writer-Sperre abruft, werden andere Threads, die auch Zugriff auf die Ressource müssen blockiert, bis der Writer die Sperre aufhebt. Die `reader_writer_lock` Klasse ist ein Beispiel für eine *Write-Preference* Sperre, dabei eine Sperre, die wartende Schreiber Blockierung aufgehoben wird handelt, bevor es hebt die Blockierung wartender Leser.

Wie die `critical_section` -Klasse, die `reader_writer_lock` -Klasse ist nicht wiedereintrittsfähig. Die [Concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock) und [Concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read) Methoden lösen eine Ausnahme vom Typ `improper_lock` Wenn sie von einem Thread aufgerufen werden, die bereits im Besitz die Sperre.

> [!NOTE]
>  Da die `reader_writer_lock` -Klasse ist nicht wiedereintrittsfähig, können Sie eine ReadOnly-Sperre auf einer Reader-/Writer-Sperre zu aktualisieren oder eine Reader-/Writer-Sperre in eine ReadOnly-Sperre. Ausführen einer dieser Vorgänge erzeugt folgende Verhalten möglicherweise undefiniert.

### <a name="methods-and-features"></a>Methoden und Funktionen

Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `reader_writer_lock` Klasse.

|Methode|Beschreibung|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|Ruft die Lese-/Schreibzugriff auf die Sperre ab.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Versucht, Lese-/Schreibzugriff auf die Sperre abzurufen, aber nicht blockiert.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Ruft schreibgeschützten Zugriff auf die Sperre ab.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Versucht, schreibgeschützten Zugriff auf die Sperre abzurufen, aber nicht blockiert.|
|[unlock](reference/reader-writer-lock-class.md#unlock)|Gibt die Sperre frei.|

[[Nach oben](#top)]

##  <a name="scoped_lock"></a> Scoped_lock und scoped_lock_read

Die `critical_section` und `reader_writer_lock` Klassen bieten geschachtelte Hilfsklassen, mit denen vereinfachen, wie Sie mit Objekten der wechselseitigen Ausschluss bewirkt arbeiten. Diese Hilfsklassen werden als bezeichnet *bewertete Sperren*.

Die `critical_section` -Klasse enthält die [Concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) Klasse. Der Konstruktor erhält Zugriff auf die bereitgestellte `critical_section` Objekt; der Destruktor Versionen Zugriff auf dieses Objekt. Die `reader_writer_lock` -Klasse enthält die [Concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) -Klasse, die ähnelt `critical_section::scoped_lock`, außer dass er über Schreibzugriff auf die bereitgestellte verwaltet `reader_writer_lock` Objekt. Die `reader_writer_lock` Klasse enthält auch die [Concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) Klasse. Diese Klasse verwaltet den Lesezugriff auf die bereitgestellte `reader_writer_lock` Objekt.

Bewertete Sperren bieten mehrere Vorteile bei der Arbeit mit `critical_section` und `reader_writer_lock` Objekte manuell. In der Regel weisen Sie eine bewertete Sperre auf dem Stapel. Eine bewertete Sperre frei Zugriff auf das gegenseitige Ausschlussobjekt automatisch, wenn es zerstört wird; aus diesem Grund wird das zugrunde liegende Objekt nicht manuell entsperrt. Dies ist nützlich, wenn eine Funktion mehrere enthält `return` Anweisungen. Bewertete Sperren können auch ausnahmesicheren Code zu schreiben. Wenn eine `throw` Anweisung bewirkt, dass des Stapels entladen und der Destruktor für jede aktive bewertete Sperre wird aufgerufen, das gegenseitige Ausschlussobjekt wird daher immer ordnungsgemäß freigegeben.

> [!NOTE]
>  Bei Verwendung der `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, und `reader_writer_lock::scoped_lock_read` Klassen nicht manuell den Zugriff auf das zugrunde liegende Objekt für den gegenseitigen Ausschluss frei. Dadurch kann die Laufzeit in einem ungültigen Zustand versetzt werden.

##  <a name="event"></a> Ereignis

Die [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) Klasse stellt ein Synchronisierungsobjekt, deren Zustand signalisiert oder nicht signalisiert werden kann. Im Gegensatz zu Synchronisierungsobjekte, z. B. kritische Abschnitte, deren Zweck besteht, die Zugriff auf freigegebene Daten zu schützen, synchronisieren Ereignisse den Ablauf der Ausführung.

Die `event` Klasse ist hilfreich, wenn eine Aufgabe für eine andere Aufgabe abgeschlossen ist. Eine Aufgabe kann eine andere Aufgabe z. B. darauf hinweisen, dass sie Daten über eine Netzwerkverbindung oder aus einer Datei gelesen hat.

### <a name="methods-and-features"></a>Methoden und Funktionen

Die folgende Tabelle zeigt einige der wichtigen Methoden, die von definiert sind die `event` Klasse.

|Methode|Beschreibung|
|------------|-----------------|
|[wait](reference/event-class.md#wait)|Wartet, bis das Ereignis signalisiert wird.|
|[set](reference/event-class.md#set)|Legt das Ereignis auf den signalisierten Zustand fest.|
|[reset](reference/event-class.md#reset)|Legt das Ereignis in den nicht signalisierten Zustand fest.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Wartet, bis mehrere Ereignisse signalisiert werden.|

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der `event` Klasse, finden Sie unter [Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Nach oben](#top)]

## <a name="related-sections"></a>Verwandte Abschnitte

[Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Das Verhalten von den durch die Windows-API bereitgestellten Synchronisierungsdatenstrukturen verglichen.

[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)<br/>
Beschreibt die Concurrency Runtime, die die parallele Programmierung vereinfacht, und stellt Links zu verwandten Themen bereit.

