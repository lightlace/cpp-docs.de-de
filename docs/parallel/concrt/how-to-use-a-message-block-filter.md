---
title: "Gewusst wie: Verwenden eines Nachrichtenblockfilters"
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
  - "Nachrichtenblockfilter, Verwenden [Concurrency Runtime]"
  - "Verwenden von Nachrichtenblockfiltern [Concurrency Runtime]"
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden eines Nachrichtenblockfilters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird veranschaulicht, wie mit einer Filterfunktion ermöglicht wird, dass ein asynchroner Nachrichtenblock eine Nachricht auf der Grundlage der Nutzlast dieser Nachricht annimmt oder ablehnt.  
  
 Beim Erstellen einer Nachrichtenblockobjekt wie z. B. eine [Concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md), ein [Concurrency:: Call](../../parallel/concrt/reference/call-class.md), oder eine [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md), können Sie angeben einer *filter-Funktion* der bestimmt, ob die Nachrichtenblock Meldung akzeptiert oder eine zurückweist. Eine Filterfunktion ist eine hilfreiche Möglichkeit, um sicherzustellen, dass nur bestimmte Werte von einem Nachrichtenblock empfangen werden.  
  
 Filterfunktionen sind wichtig, da sie Sie zum Verbinden von Nachrichtenblöcken Formular ermöglichen *Datenflussnetzwerke*. Nachrichtenblöcke in einem Datenflussnetzwerk steuern den Datenfluss, indem sie nur Nachrichten verarbeiten, die bestimmte Kriterien erfüllen. Vergleichen Sie dies mit dem Ablaufsteuerungsmodell, in dem der Datenfluss mit Steuerungsstrukturen, z. B. Bedingungsanweisungen, Schleifen usw., gesteuert wird.  
  
 Dieses Dokument enthält ein einfaches Beispiel für die Verwendung eines Nachrichtenfilters. Weitere Beispiele, mit denen Nachrichtenfilter und das Datenflussmodell zum Verbinden von Nachrichtenblöcken finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) und [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
## <a name="example"></a>Beispiel  
 Betrachten Sie die folgende Funktion `count_primes`, die die grundlegende Verwendung eines Nachrichtenblocks veranschaulicht, der keine eingehenden Nachrichten filtert. Der Nachrichtenblock fügt Primzahlen eine [Std:: vector](vector%20Class.md) Objekt. Die `count_primes`-Funktion sendet Zahlen an den Nachrichtenblock, empfängt die Ausgabewerte des Nachrichtenblocks und gibt die Zahlen, die Primzahlen sind, an die Konsole aus.  
  
 [!CODE [concrt-primes-filter#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-primes-filter#1)]  
  
 Das `transformer`-Objekt verarbeitet alle Eingabewerte. Es benötigt jedoch nur die Werte, bei denen es sich um Primzahlen handelt. Die Anwendung kann zwar so geschrieben werden kann, dass der Nachrichtenabsender nur Primzahlen sendet, jedoch können die Anforderungen des Nachrichtenempfängers nicht immer bekannt sein.  
  
## <a name="example"></a>Beispiel  
 Die folgende Funktion `count_primes_filter` führt die gleiche Aufgabe wie die `count_primes`-Funktion aus. Das `transformer`-Objekt in dieser Version verwendet jedoch eine Filterfunktion, damit nur die Werte angenommen werden, die Primzahlen sind. Die Funktion, die die Aktion ausführt, empfängt nur Primzahlen. Daher muss sie die `is_prime`-Funktion nicht aufrufen.  
  
 Da das `transformer`-Objekt nur Primzahlen empfängt, kann das `transformer`-Objekt selbst die Primzahlen enthalten. Das bedeutet, dass das `transformer`-Objekt in diesem Beispiel nicht benötigt wird, um dem `vector`-Objekt die Primzahlen hinzuzufügen.  
  
 [!CODE [concrt-primes-filter#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-primes-filter#2)]  
  
 Das `transformer`-Objekt verarbeitet jetzt nur die Werte, die Primzahlen sind. Im vorherigen Beispiel verarbeitet das `transformer`-Objekt alle Nachrichten. Daher muss im vorherigen Beispiel die gleiche Anzahl von Nachrichten empfangen werden, wie gesendet wurden. In diesem Beispiel wird anhand des Ergebnisses der [Concurrency:: Send](../Topic/send%20Function.md) Funktion, um zu bestimmen, wie viele Nachrichten empfangen aus der `transformer` Objekt. Die `send`-Funktion gibt `true` zurück, wenn der Nachrichtenpuffer die Nachricht annimmt, und `false`, wenn der Nachrichtenpuffer die Nachricht ablehnt. Daher stimmt die Häufigkeit, mit der der Nachrichtenpuffer die Nachricht annimmt, mit der Anzahl der Primzahlen überein.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht das vollständige Beispiel. In dem Beispiel werden die `count_primes`-Funktion und die `count_primes_filter`-Funktion aufgerufen.  
  
 [!CODE [concrt-primes-filter#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-primes-filter#3)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `primes-filter.cpp` und dann den folgenden Befehl in einer Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc Primes-filter.cpp**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Eine Filterfunktion kann eine Lambda-Funktion, ein Funktionsobjekt oder ein Funktionszeiger sein. Jede Filterfunktion nimmt eines der folgenden Formate an:  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Um das unnötige Kopieren von Daten zu vermeiden, verwenden Sie das zweite Format bei einem aggregierten Typ, der anhand des Werts übertragen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Transformer-Klasse](../../parallel/concrt/reference/transformer-class.md)
