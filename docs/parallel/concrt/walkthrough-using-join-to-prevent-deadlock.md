---
title: "Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join"
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
  - "Verhindern von Deadlocks bei Joins [Concurrency Runtime]"
  - "Deadlocks, Verhindern [Concurrency Runtime]"
  - "Nicht gierige Joins, Beispiel"
  - "join-Klasse, Beispiel"
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
caps.latest.revision: 16
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird anhand des Philosophenproblems illustriert, wie sich mit der [concurrency::join](../../parallel/concrt/reference/join-class.md)\-Klasse Deadlocks in der Anwendung verhindern lassen.  In einer Softwareanwendung tritt ein *Deadlock* auf, wenn mindestens zwei Prozesse jeweils über eine Ressource verfügen und warten, bis von einem anderen Prozess eine weitere Ressource freigegeben wird.  
  
 Das Philosophenproblem ist ein spezifisches Beispiel dafür, welche Probleme allgemein auftreten können, wenn ein Satz von Ressourcen von mehreren gleichzeitig ablaufenden Prozessen gemeinsam verwendet wird.  
  
## Vorbereitungsmaßnahmen  
 Lesen Sie sich folgende Themen durch, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
-   [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)  
  
-   [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
-   [Das Philosophenproblem](#problem)  
  
-   [Eine naive Implementierung](#deadlock)  
  
-   [Verhindern von Deadlocks mit join](#solution)  
  
##  <a name="problem"></a> Das Philosophenproblem  
 Das Philosophenproblem veranschaulicht, wie Deadlocks in einer Anwendung auftreten.  Bei diesem Problem sitzen fünf Philosophen an einem runden Tisch.  Die einzelnen Philosophen haben Phasen, in denen sie denken, und Phasen, in denen sie essen.  Jeder Philosoph muss ein Essstäbchen mit dem Tischnachbarn zu seiner Linken und ein anderes Essstäbchen mit dem Tischnachbarn zu seiner Rechten teilen.  Die folgende Abbildung veranschaulicht diese Anordnung.  
  
 ![Das Philosophenproblem](../../parallel/concrt/media/dining_philosophersproblem.png "Dining\_PhilosophersProblem")  
  
 Um essen zu können, benötigt ein Philosoph zwei Essstäbchen.  Wenn jeder Philosoph nur ein Essstäbchen hat und auf das zweite wartet, kann kein Philosoph essen und alle bleiben hungrig.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="deadlock"></a> Eine naive Implementierung  
 Im folgenden Beispiel wird eine naive Implementierung des Philosophenproblems veranschaulicht.  Durch die `philosopher`\-Klasse, die von [concurrency::agent](../../parallel/concrt/reference/agent-class.md) abgeleitet wird, kann jeder Philosoph unabhängig handeln.  Im Beispiel wird ein freigegebenes Array von [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md)\-Objekten verwendet, damit jedes `philosopher`\-Objekt exklusiven Zugriff auf ein Paar Essstäbchen hat.  
  
 Um die Implementierung mit der Abbildung in Verbindung zu bringen, stellt die `philosopher`\-Klasse einen Philosophen dar.  Jedes Essstäbchen wird durch eine `int`\-Variable dargestellt.  Die `critical_section`\-Objekte dienen als Halter für die Essstäbchen.  Die `run`\-Methode simuliert das Leben des Philosophen.  Die `think`\-Methode simuliert das Denken und die `eat`\-Methode das Essen.  
  
 Ein `philosopher`\-Objekt sperrt beide `critical_section`\-Objekte, um das Herausnehmen der Essstäbchen aus den Haltern zu simulieren, bevor die `eat`\-Methode aufgerufen wird.  Nach dem Aufruf von `eat` werden die Essstäbchen wieder vom `philosopher`\-Objekt in die Halter zurückgelegt, und zwar durch Zurücksetzen der `critical_section`\-Objekte in den entsperrten Zustand.  
  
 Die `pickup_chopsticks`\-Methode veranschaulicht, wo ein Deadlock auftreten kann.  Wenn jedes `philosopher`\-Objekt Zugriff auf eine der Sperren erlangt, kann kein `philosopher`\-Objekt fortfahren, weil die andere Sperre von einem anderen `philosopher`\-Objekt gesteuert wird.  
  
## Beispiel  
  
### **Beschreibung**  
  
### Code  
 [!CODE [concrt-philosophers-deadlock#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-deadlock#1)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `philosophers-deadlock.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc philosophers\-deadlock.cpp**  
  
 \[[Nach oben](#top)\]  
  
##  <a name="solution"></a> Verhindern von Deadlocks mit join  
 In diesem Abschnitt wird gezeigt, wie Meldungspuffer und Meldungsübergabefunktionen verwendet werden, um Deadlocks zu vermeiden.  
  
 Um dieses Beispiel mit dem früheren in Verbindung zu bringen, ersetzt die `philosopher`\-Klasse alle `critical_section`\-Objekte durch ein [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)\-Objekt und ein `join`\-Objekt.  Das `join`\-Objekt dient als Vermittler, das dem Philosophen die Essstäbchen bereitstellt.  
  
 In diesem Beispiel wird die `unbounded_buffer`\-Klasse verwendet, da die Meldung aus der Meldungswarteschlange entfernt wird, wenn ein Ziel eine Meldung von einem `unbounded_buffer`\-Objekt empfängt.  So kann ein `unbounded_buffer`\-Objekt, das eine Meldung enthält, darauf hinweisen, dass das Essstäbchen zur Verfügung steht.  Ein `unbounded_buffer`\-Objekt, das keine Meldung enthält, weist darauf hin, dass das Essstäbchen verwendet wird.  
  
 In diesem Beispiel wird ein nicht gieriges `join`\-Objekt verwendet, da ein nicht gieriger Join nur dann jedem `philosopher`\-Objekt Zugriff auf beide Essstäbchen gewährt, wenn beide `unbounded_buffer`\-Objekte eine Meldung enthalten.  Ein gieriger Join würde Deadlocks nicht verhindern, da Meldungen von ihm akzeptiert werden, sobald sie verfügbar sind.  Deadlocks können auftreten, wenn alle gierigen `join`\-Objekte eine der Meldungen empfangen, aber ewig warten, bis die andere verfügbar wird.  
  
 Weitere Informationen zu gierigen und nicht gierigen Joins sowie zu den Unterschieden zwischen den verschiedenen Meldungspuffertypen finden Sie unter [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
#### So verhindern Sie Deadlocks in diesem Beispiel  
  
1.  Entfernen Sie folgenden Code aus dem Beispiel.  
  
     [!CODE [concrt-philosophers-deadlock#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-deadlock#2)]  
  
2.  Ändern Sie den Typ der Datenmember `_left` und `_right` der `philosopher`\-Klasse in `unbounded_buffer`.  
  
     [!CODE [concrt-philosophers-join#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#2)]  
  
3.  Ändern Sie den `philosopher`\-Konstruktor, damit `unbounded_buffer`\-Objekte als Parameter verwendet werden.  
  
     [!CODE [concrt-philosophers-join#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#3)]  
  
4.  Ändern Sie die `pickup_chopsticks`\-Methode, um ein nicht gieriges `join`\-Objekt zum Empfangen von Meldungen von den Meldungspuffern für beide Essstäbchen.  
  
     [!CODE [concrt-philosophers-join#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#4)]  
  
5.  Ändern Sie die `putdown_chopsticks`\-Methode, um den Zugriff auf die Essstäbchen freizugeben, indem eine Meldung an die Meldungspuffer für beide Essstäbchen gesendet wird.  
  
     [!CODE [concrt-philosophers-join#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#5)]  
  
6.  Ändern Sie die `run`\-Methode, um die Ergebnisse der `pickup_chopsticks`\-Methode aufzunehmen und diese Ergebnisse an die `putdown_chopsticks`\-Methode weiterzuleiten.  
  
     [!CODE [concrt-philosophers-join#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#6)]  
  
7.  Ändern Sie die Deklaration der `chopsticks`\-Variable in der `wmain`\-Funktion, damit sie ein Array von `unbounded_buffer`\-Objekten ist, die jeweils über eine Meldung verfügen.  
  
     [!CODE [concrt-philosophers-join#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#7)]  
  
## Beispiel  
  
### **Beschreibung**  
 Nachfolgend sehen Sie das vollständige Beispiel, bei dem nicht gierige `join`\-Objekte verwendet werden, um das Risiko von Deadlocks auszuschließen.  
  
### Code  
 [!CODE [concrt-philosophers-join#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#1)]  
  
### Kommentare  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **aristotle ate 50 times.**  
**descartes ate 50 times.**  
**hobbes ate 50 times.**  
**socrates ate 50 times.**  
**plato ate 50 times.**   
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `philosophers-join.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc philosophers\-join.cpp**  
  
 \[[Nach oben](#top)\]  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)   
 [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)