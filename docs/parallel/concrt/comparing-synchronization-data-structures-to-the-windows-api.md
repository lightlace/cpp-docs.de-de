---
title: "Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API"
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
  - "Synchronisierungsdatenstrukturen, Vergleich mit der Windows-API"
  - "event-Klasse, Beispiel"
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
caps.latest.revision: 16
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird das Verhalten der von der Concurrency Runtime bereitgestellten Synchronisierungsdatenstrukturen mit den von der Windows\-API bereitgestellten Synchronisierungsdatenstrukturen verglichen.  
  
 Die von der Concurrency Runtime bereitgestellten Synchronisierungsdatenstrukturen basieren auf dem *kooperativen Threadingmodell*.  Im kooperativen Threadingmodell halten Synchronisierungsprimitiven ihre Verarbeitungsressourcen zugunsten von anderen Threads explizit zurück.  Dies unterscheidet sich vom *präemptiven Threadingmodell*, bei dem Verarbeitungsressourcen vom Planer oder vom Betriebssystem an andere Threads übergeben werden.  
  
## critical\_section  
 Die [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md)\-Klasse ähnelt der `CRITICAL_SECTION`\-Struktur in Windows, da sie nur von den Threads eines Prozesses verwendet werden kann.  Weitere Informationen zu kritischen Abschnitten in der Windows\-API finden Sie unter [Critical Section Objects](http://msdn.microsoft.com/library/windows/desktop/ms682530).  
  
## reader\_writer\_lock  
 Die [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)\-Klasse ähnelt der Reader\-\/Writer\-Sperre \(Slim Reader\/Writer, SRW\) in Windows.  In der folgenden Tabelle werden die Übereinstimmungen und Unterschiede aufgelistet.  
  
|Feature|`reader_writer_lock`|SRW\-Sperre|  
|-------------|--------------------------|-----------------|  
|Nicht wiedereintretend|ja|ja|  
|Kann einen Reader auf einen Writer hochstufen|nein|nein|  
|Kann einen Writer auf einen Reader tieferstufen|nein|nein|  
|write\-preference\-Sperre|ja|nein|  
|FIFO\-Zugriff auf Writer|ja|nein|  
  
 Weitere Informationen zu SRW\-Sperren finden Sie unter [Slim Reader\/Writer \(SRW\) Locks](http://msdn.microsoft.com/library/windows/desktop/aa904937) im Platform SDK.  
  
## Ereignis  
 Die [concurrency::event](../../parallel/concrt/reference/event-class.md)\-Klasse ähnelt einem nicht benannten Ereignis für manuelles Zurücksetzen in Windows.  Das Verhalten eines `event`\-Objekts ist jedoch kooperativ, das Verhalten eines Windows\-Ereignisses hingegen präemptiv.  Weitere Informationen zu Windows\-Ereignissen finden Sie unter [Event Objects](http://msdn.microsoft.com/library/windows/desktop/ms682655).  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Beispiel soll den Unterschied zwischen der `event`\-Klasse und Windows\-Ereignissen verdeutlichen.  In diesem Beispiel wird der Planer aktiviert, um höchstens zwei gleichzeitige Aufgaben zu erstellen. Anschließend werden zwei ähnliche Funktionen aufgerufen, die die `event`\-Klasse und ein Ereignis für manuelles Zurücksetzen in Windows verwenden.  Beide Funktionen erstellen zunächst mehrere Aufgaben, die auf die Signalisierung eines freigegebenen Ereignisses warten.  Beide Funktionen halten dann die ausgeführten Aufgaben zurück und signalisieren das Ereignis.  Beide Funktionen warten dann auf das signalisierte Ereignis.  
  
### Code  
 [!CODE [concrt-event-comparison#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-event-comparison#1)]  
  
### Kommentare  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
  **Cooperative event:**  
 **Context 0: waiting on an event.**  
 **Context 1: waiting on an event.**  
 **Context 2: waiting on an event.**  
 **Context 3: waiting on an event.**  
 **Context 4: waiting on an event.**  
 **Setting the event.**  
 **Context 5: received the event.**  
 **Context 6: received the event.**  
 **Context 7: received the event.**  
 **Context 8: received the event.**  
 **Context 9: received the event.**  
**Windows event:**  
 **Context 10: waiting on an event.**  
 **Context 11: waiting on an event.**  
 **Setting the event.**  
 **Context 12: received the event.**  
 **Context 14: waiting on an event.**  
 **Context 15: received the event.**  
 **Context 16: waiting on an event.**  
 **Context 17: received the event.**  
 **Context 18: waiting on an event.**  
 **Context 19: received the event.**  
 **Context 13: received the event.** Da das Verhalten der `event`\-Klasse kooperativ ist, kann der Planer Verarbeitungsressourcen einem anderen Kontext zuweisen, während auf die Signalisierung eines Ereignisses gewartet wird.  Aus diesem Grund bewerkstelligt die Version, die die `event`\-Klasse verwendet, einen höheren Arbeitsaufwand.  In der Version, die Windows\-Ereignisse verwendet, muss jede wartende Aufgabe den signalisierten Zustand aufweisen, bevor die nächste Aufgabe gestartet werden kann.  
  
 Weitere Informationen zu Aufgaben finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Siehe auch  
 [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)   
 [Kritische Abschnittsobjekte](http://msdn.microsoft.com/library/windows/desktop/ms682530)   
 [SRW\-Sperren \(Slim Reader\/Writer\)](http://msdn.microsoft.com/library/windows/desktop/aa904937)   
 [Ereignisobjekte](http://msdn.microsoft.com/library/windows/desktop/ms682655)