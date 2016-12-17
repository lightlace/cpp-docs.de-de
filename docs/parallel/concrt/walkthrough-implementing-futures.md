---
title: "Exemplarische Vorgehensweise: Implementieren von Futures"
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
  - "Implementieren von Futures [Concurrency Runtime]"
  - "Futures, Implementieren [Concurrency Runtime]"
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: 25
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Implementieren von Futures
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema erfahren Sie, wie Sie Futures in Ihre Anwendung implementieren. Es wird veranschaulicht, wie Sie die vorhandenen Funktionen in der Concurrency Runtime kombinieren können, um mehr Funktionalität zu erzielen.  
  
> [!IMPORTANT]
>  In diesem Thema wird das Konzept von Futures zu Demonstrationszwecken veranschaulicht. Wir empfehlen die Verwendung [Std:: Future](../../standard-library/future-class.md) oder [Concurrency:: Task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) Wenn Sie eine asynchrone Aufgabe, die einen Wert zur späteren Verwendung berechnet benötigen.  
  
 Ein *Aufgabe* ist eine Berechnung, die in weitere, differenziertere Berechnungen unterteilt werden kann. Ein *zukünftige* ist eine asynchrone Aufgabe, die einen Wert zur späteren Verwendung berechnet.  
  
 Zur Implementierung von Futures wird in diesem Thema die `async_future`-Klasse definiert. Die `async_future` Klasse verwendet die folgenden Komponenten der Concurrency Runtime: die [Concurrency:: task_group](../Topic/task_group%20Class.md) Klasse und die [Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) Klasse. Die `async_future`-Klasse verwendet die `task_group`-Klasse zur asynchronen Berechnung eines Werts und die `single_assignment`-Klasse zum Speichern des Ergebnisses. Der Konstruktor der `async_future`-Klasse akzeptiert eine Arbeitsfunktion, die das Ergebnis berechnet, das mit der `get`-Methode abgerufen wird.  
  
### <a name="to-implement-the-asyncfuture-class"></a>So implementieren Sie die async_future-Klasse  
  
1.  Deklarieren Sie eine Vorlagenklasse mit dem Namen `async_future`, die auf der Grundlage des Typs der resultierenden Berechnung parametrisiert wird. Fügen Sie der Klasse einen `public`-Abschnitt und einen `private`-Abschnitt hinzu.  
  
 [!CODE [concrt-futures#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures#2)]  
  
2.  Deklarieren Sie im `private`-Abschnitt der `async_future`-Klasse ein `task_group`-Datenmember und ein `single_assignment`-Datenmember.  
  
 [!CODE [concrt-futures#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures#3)]  
  
3.  Implementieren Sie im `public`-Abschnitt der `async_future`-Klasse den Konstruktor. Der Konstruktor ist eine Vorlage, die auf Grundlage der Arbeitsfunktion, die zur Berechnung des Ergebnisses dient, parametrisiert wird. Der Konstruktor führt die Arbeitsfunktion in asynchron die `task_group` -Datenmember aus und verwendet die [Concurrency:: Send](../Topic/send%20Function.md) Funktion schreibt das Ergebnis der `single_assignment` -Datenmember.  
  
 [!CODE [concrt-futures#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures#4)]  
  
4.  Implementieren Sie im `public`-Abschnitt der `async_future`-Klasse den Destruktor. Der Destruktor wartet auf das Beenden der Aufgabe.  
  
 [!CODE [concrt-futures#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures#5)]  
  
5.  Implementieren Sie im `public`-Abschnitt der `async_future`-Klasse die `get`-Methode. Diese Methode verwendet die [Concurrency:: Receive](../Topic/receive%20Function.md) Funktion, die das Ergebnis der Arbeitsfunktion abrufen.  
  
 [!CODE [concrt-futures#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures#6)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt die vollständige `async_future`-Klasse mit einer Verwendungsmöglichkeit. Die `wmain` -Funktion erstellt eine std::[Vektor](vector%20Class.md) -Objekt, das 10.000 zufällige Ganzzahlwerte enthält. Anschließend werden mithilfe von `async_future`-Objekten der kleinste und der größte Wert im `vector`-Objekt gesucht.  
  
### <a name="code"></a>Code  
 [!CODE [concrt-futures#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures#1)]  
  
### <a name="comments"></a>Kommentare  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 Im Beispiel werden die Ergebnisse der Berechnung mit der `async_future::get`-Methode abgerufen. Die `async_future::get`-Methode wartet, bis die Berechnung beendet ist.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Erweitern der `async_future` Klasse zum Behandeln von Ausnahmen, die von der Arbeitsfunktion ausgelöst werden, ändern die `async_future::get` Methode aufrufen, die [Concurrency:: task_group::](../Topic/task_group::wait%20Method.md) Methode. Die `task_group::wait`-Methode löst alle von der Arbeitsfunktion generierten Ausnahmen aus.  
  
 Das folgende Beispiel zeigt die geänderte Version der `async_future`-Klasse. Die `wmain` Funktion verwendet eine `try`-`catch` Block, um das Ergebnis der `async_future` Objekt oder den Wert der Ausnahme auszugeben, die von der Arbeitsfunktion generiert wird.  
  
 [!CODE [concrt-futures-with-eh#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-futures-with-eh#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
caught exception: error  
```  
  
 Weitere Informationen zum Ausnahmebehandlungsmodell in der Concurrency Runtime finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `futures.cpp` und dann den folgenden Befehl in ein Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc futures.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime Exemplarische Vorgehensweisen](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Behandlung von Ausnahmen](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Task_group-Klasse](../Topic/task_group%20Class.md)   
 [Single_assignment-Klasse](../../parallel/concrt/reference/single-assignment-class.md)
