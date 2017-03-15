---
title: "Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kooperatives Implementieren von Semaphoren"
  - "context-Klasse"
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird gezeigt, wie die Concurrency:: Context-Klasse zum Implementieren einer kooperativen Semaphore-Klasse verwenden.  
  
 Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Das Blockieren oder Zurückhalten des aktuellen Kontexts ist nützlich, wenn der aktuelle Kontext nicht fortfahren kann, da eine Ressource nicht verfügbar ist. Ein *Semaphore* ist ein Beispiel für eine Situation, in der aktuelle Ausführungskontext warten muss eine Ressource verfügbar wird. Eine Semaphore ist wie ein kritisches Abschnittsobjekt ein Synchronisierungsobjekt, das dem Code in einem Kontext ermöglicht, exklusiv auf eine Ressource zuzugreifen. Im Gegensatz zu einem kritischen Abschnittsobjekt ermöglicht eine Semaphore jedoch mehr als einem Kontext, gleichzeitig auf die Ressource zuzugreifen. Wenn die maximale Anzahl von Kontexten eine Semaphorensperre hat, muss jeder zusätzliche Kontext warten, bis ein anderer Kontext die Sperre aufhebt.  
  
### <a name="to-implement-the-semaphore-class"></a>So implementieren Sie die Semaphorenklasse  
  
1.  Deklarieren Sie eine Klasse mit dem Namen `semaphore`. Fügen Sie der Klasse einen `public`-Abschnitt und einen `private`-Abschnitt hinzu.  
  
 [!CODE [concrt-cooperative-semaphore#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#1)]  
  
2.  In der `private` Teil der `semaphore` Klasse, deklarieren Sie eine [Std:: Atomic](../../standard-library/atomic-structure.md) Variablen, die die Semaphorenanzahl enthält und ein [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) -Objekt, das die Kontexte enthält, die auf das Abrufen der Semaphore warten müssen.  
  
 [!CODE [concrt-cooperative-semaphore#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#2)]  
  
3.  Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse den Konstruktor. Der Konstruktor akzeptiert einen `long long`-Wert, der die maximale Anzahl von Kontexten angibt, die gleichzeitig über die Sperre verfügen können.  
  
 [!CODE [concrt-cooperative-semaphore#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#3)]  
  
4.  Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse die `acquire`-Methode. Diese Methode dekrementiert die Semaphorenanzahl als atomaren Vorgang. Wenn die Semaphorenanzahl negativ wird, fügen Sie den aktuellen Kontext am Ende der Warteschlange und rufen die [Concurrency::Context::Block](../Topic/Context::Block%20Method.md) Methode, um den aktuellen Kontext zu blockieren.  
  
 [!CODE [concrt-cooperative-semaphore#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#4)]  
  
5.  Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse die `release`-Methode. Diese Methode inkrementiert die Semaphorenanzahl als atomaren Vorgang. Wenn die Semaphorenanzahl vor dem Inkrementieren negativ ist, gibt es mindestens einen Kontext, der auf die Sperre wartet. Entsperren Sie in diesem Fall den Kontext, der sich am Anfang der Warteschlange befindet.  
  
 [!CODE [concrt-cooperative-semaphore#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#5)]  
  
## <a name="example"></a>Beispiel  
 Die `semaphore`-Klasse in diesem Beispiel verhält sich kooperativ, da die `Context::Block`-Methode und `Context::Yield`-Methode die Ausführung zurückhalten, damit die Laufzeit andere Aufgaben ausführen kann.  
  
 Die `acquire`-Methode dekrementiert den Zähler, es kann jedoch sein, dass sie das Hinzufügen des Kontexts zur Warteschlange noch nicht abgeschlossen hat, bevor ein anderer Kontext die `release`-Methode aufruft. Um dies zu berücksichtigen die `release` Methode verwendet eine Spinschleife, die [yield](../Topic/Context::Yield%20Method.md) Methode zu warten die `acquire` -Methode zum Hinzufügen des Kontexts abgeschlossen.  
  
 Die `release`-Methode kann die `Context::Unblock`-Methode aufrufen, bevor die `acquire`-Methode die `Context::Block`-Methode aufruft. Sie müssen keinen Schutz vor dieser Racebedingung implementieren, da die Laufzeit diesen Methoden ermöglicht, in beliebiger Reihenfolge aufgerufen zu werden. Wenn die `release`-Methode `Context::Unblock` aufruft, bevor die `acquire`-Methode `Context::Block` für den gleichen Kontext aufruft, bleibt dieser Kontext weiterhin unblockiert. Die Laufzeit erfordert nur, dass für jeden Aufruf von `Context::Block` ein entsprechender Aufruf von `Context::Unblock` vorhanden ist.  
  
 Im folgenden Beispiel wird die vollständige `semaphore`-Klasse dargestellt. Die `wmain`-Funktion zeigt die grundlegende Verwendung dieser Klasse. Die `wmain` -Funktion verwendet die [Concurrency:: parallel_for](../Topic/parallel_for%20Function.md) -Algorithmus mehrere Aufgaben, die Zugriff auf die Semaphore benötigen. Da drei Threads jederzeit über die Sperre verfügen können, müssen einige Aufgaben warten, bis eine andere Aufgabe abgeschlossen ist und die Sperre freigibt.  
  
 [!CODE [concrt-cooperative-semaphore#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#6)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
```Output  
In loop iteration 5...  
In loop iteration 0...  
In loop iteration 6...  
In loop iteration 1...  
In loop iteration 2...  
In loop iteration 7...  
In loop iteration 3...  
In loop iteration 8...  
In loop iteration 9...  
In loop iteration 4...  
```  
  
 Weitere Informationen zu den `concurrent_queue` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md). Weitere Informationen zu den `parallel_for` -Algorithmus finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `cooperative-semaphore.cpp` und dann den folgenden Befehl in einer Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc Cooperative-semaphore.cpp**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Können Sie die *Resource Acquisition Is Initialization* (RAII)-Muster zur Beschränkung des Zugriffs auf ein `semaphore` Objekt auf einen bestimmten Gültigkeitsbereich. Unter dem RAII-Muster wird dem Stapel eine Datenstruktur zugeordnet. Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird. Das RAII-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird. Daher wird die Ressource ordnungsgemäß verwaltet, wenn eine Ausnahme ausgelöst wird, oder wenn eine Funktion mehrere `return`-Anweisungen enthält.  
  
 Im folgenden Beispiel wird eine Klasse mit dem Namen `scoped_lock` definiert, die im `public`-Abschnitt der `semaphore`-Klasse definiert ist. Die `scoped_lock` -Klasse ähnelt der [Concurrency::critical_section::scoped_lock](../Topic/critical_section::scoped_lock%20Class.md) und [Concurrency::reader_writer_lock::scoped_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md) Klassen. Der Konstruktor der `semaphore::scoped_lock`-Klasse erhält Zugriff auf das angegebene `semaphore`-Objekt, und der Destruktor gibt den Zugriff auf dieses Objekt frei.  
  
 [!CODE [concrt-cooperative-semaphore#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#7)]  
  
 Im folgenden Beispiel wird der Text der Arbeitsfunktion geändert, die an den `parallel_for`-Algorithmus übergeben wird, damit RAII verwendet wird um sicherzustellen, dass die Semaphore vor der Rückkehr der Funktion freigegeben wird. Durch diese Methode wird sichergestellt, dass die Arbeitsfunktion sicher vor Ausnahmen ist.  
  
 [!CODE [concrt-cooperative-semaphore#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-semaphore#8)]  
  
## <a name="see-also"></a>Siehe auch  
 [Kontexte](../../parallel/concrt/contexts.md)   
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)

