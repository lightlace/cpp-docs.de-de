---
title: "Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung"
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
  - "Asynchrone Agents, Erstellen"
  - "agent-Klasse, Beispiel"
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 24
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die Erstellung einer einfachen agentbasierten Anwendung beschrieben.  In dieser exemplarischen Vorgehensweise können Sie einen Agent erstellen, der Daten asynchron aus einer Textdatei ausliest.  Die Anwendung berechnet die Prüfsumme des Inhalts dieser Datei mithilfe des Adler\-32\-Prüfsummenalgorithmus.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise sollten Sie die folgenden Themen lesen:  
  
-   [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)  
  
-   [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Abschnitte  
 Mit dieser exemplarischen Vorgehensweise wird die Durchführung der folgenden Aufgaben beschrieben:  
  
-   [Erstellen der Konsolenanwendung](#createApplication)  
  
-   [Erstellen der file\_reader\-Klasse](#createAgentClass)  
  
-   [Verwenden der file\_reader\-Klasse in der Anwendung](#useAgentClass)  
  
##  <a name="createApplication"></a> Erstellen der Konsolenanwendung  
 In diesem Abschnitt wird die Erstellung einer Visual C\+\+\-Konsolenanwendung beschrieben, die auf die vom Programm verwendeten Headerdateien verweist.  
  
#### So erstellen Sie eine Visual C\+\+\-Anwendung mit dem Win32\-Anwendungs\-Assistenten  
  
1.  Klicken Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** anzuzeigen.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** den Knoten **Visual C\+\+** aus, und wählen Sie dann im Bereich **Vorlagen** die Option **Win32\-Konsolenanwendung** aus.  Geben Sie einen Namen für das Projekt ein, z. B. `BasicAgent`, und klicken Sie dann auf **OK**, um den **Win32\-Anwendungs\-Assistenten** anzuzeigen.  
  
3.  Klicken Sie im Dialogfeld **Win32\-Anwendungs\-Assistent** auf **Fertig stellen**.  
  
4.  Fügen Sie in der Datei stdafx.h den folgenden Code hinzu.  
  
     [!CODE [concrt-basic-agent#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#1)]  
  
     Die Headerdatei agents.h enthält die Funktionen der [concurrency::agent](../../parallel/concrt/reference/agent-class.md)\-Klasse.  
  
5.  Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um die Anwendung zu erstellen.  Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debuggen** auf **Debugging starten** klicken.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="createAgentClass"></a> Erstellen der file\_reader\-Klasse  
 In diesem Abschnitt wird die Erstellung der `file_reader`\-Klasse beschrieben.  Die Runtime plant jeden Agent so, dass er Arbeiten im eigenen Kontext ausführt.  Daher können Sie einen Agent erstellen, der Arbeiten synchron ausführt, aber asynchron mit anderen Komponenten interagiert.  Die `file_reader`\-Klasse liest Daten aus einer angegebenen Eingabedatei aus und sendet Daten aus dieser Datei an eine angegebene Zielkomponente.  
  
#### So erstellen Sie die file\_reader\-Klasse  
  
1.  Fügen Sie dem Projekt eine neue C\+\+\-Headerdatei hinzu.  Klicken Sie hierzu im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Knoten **Headerdateien**, und klicken Sie auf **Hinzufügen** und dann auf **Neues Element**.  Wählen Sie im Bereich **Vorlagen** die Option **Headerdatei \(.h\)** aus.  Geben Sie im Dialogfeld **Neues Element hinzufügen** im Feld **Name** den Namen `file_reader.h` ein, und klicken Sie auf **Hinzufügen**.  
  
2.  Fügen Sie in der Datei file\_reader.h den folgenden Code hinzu.  
  
     [!CODE [concrt-basic-agent#17](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#17)]  
  
3.  Erstellen Sie in der Datei file\_reader.h eine Klasse mit dem Namen `file_reader`, die von `agent` abgeleitet wird.  
  
     [!CODE [concrt-basic-agent#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#2)]  
  
4.  Fügen Sie dem `private`\-Abschnitt der Klasse die folgenden Datenmember hinzu.  
  
     [!CODE [concrt-basic-agent#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#3)]  
  
     Der `_file_name`\-Member ist der Name der Datei, die vom Agent ausgelesen wird.  Der `_target`\-Member ist ein [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md)\-Objekt, in das der Agent den Inhalt der Datei schreibt.  Der `_error`\-Member speichert alle Fehler, die während der Lebensdauer des Agents auftreten.  
  
5.  Fügen Sie dem `public`\-Abschnitt der  `file_reader`\-Klasse den folgenden Code für die `file_reader`\-Konstruktoren hinzu.  
  
     [!CODE [concrt-basic-agent#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#4)]  
  
     Mit jeder Konstruktorüberladung werden die `file_reader`\-Datenmember festgelegt.  Mit der zweiten und dritten Konstruktorüberladung wird es der Anwendung ermöglicht, mit dem Agent einen bestimmten Planer zu verwenden.  Bei der ersten Überladung wird der Standardplaner mit dem Agent verwendet.  
  
6.  Fügen Sie dem public\-Abschnitt der `file_reader`\-Klasse die `get_error`\-Methode hinzu.  
  
     [!CODE [concrt-basic-agent#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#5)]  
  
     Die `get_error`\-Methode ruft alle Fehler ab, die während der Lebensdauer des Agents auftreten.  
  
7.  Implementieren Sie die [concurrency::agent::run](../Topic/agent::run%20Method.md)\-Methode im `protected`\-Abschnitt der Klasse.  
  
     [!CODE [concrt-basic-agent#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#6)]  
  
     Die `run`\-Methode öffnet die Datei und liest Daten aus.  Die `run`\-Methode erfasst mithilfe der Ausnahmebehandlung alle Fehler, die während der Dateiverarbeitung auftreten.  
  
     Jedes Mal, wenn diese Methode Daten aus der Datei ausliest, ruft sie die [concurrency::asend](../Topic/asend%20Function.md)\-Funktion auf, um diese Daten an den Zielpuffer zu senden.  Sie sendet die leere Zeichenfolge an den Zielpuffer, um so das Ende der Verarbeitung anzugeben.  
  
 Im folgenden Beispiel wird der vollständige Inhalt der Datei file\_reader.h dargestellt.  
  
 [!CODE [concrt-basic-agent#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#7)]  
  
 \[[Nach oben](#top)\]  
  
##  <a name="useAgentClass"></a> Verwenden der file\_reader\-Klasse in der Anwendung  
 In diesem Abschnitt wird beschrieben, wie mithilfe der `file_reader`\-Klasse der Inhalt einer Textdatei gelesen wird.  Darüber hinaus wird auch die Erstellung des [concurrency::call](../../parallel/concrt/reference/call-class.md)\-Objekts beschrieben, das diese Dateidaten empfängt und die Adler\-32\-Prüfsumme berechnet.  
  
#### So verwenden Sie die file\_reader\-Klasse in der Anwendung  
  
1.  Fügen Sie in der Datei BasicAgent.cpp die folgende `#include`\-Anweisung hinzu.  
  
     [!CODE [concrt-basic-agent#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#8)]  
  
2.  Fügen Sie in der Datei BasicAgent.cpp die folgenden `using`\-Direktiven hinzu.  
  
     [!CODE [concrt-basic-agent#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#9)]  
  
3.  Erstellen Sie in der `_tmain`\-Funktion ein [concurrency::event](../../parallel/concrt/reference/event-class.md)\-Objekt, das das Ende der Verarbeitung signalisiert.  
  
     [!CODE [concrt-basic-agent#10](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#10)]  
  
4.  Erstellen Sie ein `call`\-Objekt, das beim Empfang von Daten die Prüfsumme aktualisiert.  
  
     [!CODE [concrt-basic-agent#11](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#11)]  
  
     Dieses `call`\-Objekt legt darüber hinaus auch das `event`\-Objekt fest, wenn es die leere Zeichenfolge empfängt, um das Ende der Verarbeitung zu signalisieren.  
  
5.  Erstellen Sie ein `file_reader`\-Objekt, das aus der Datei test.txt ausliest und den Inhalt dieser Datei in das `call`\-Objekt schreibt.  
  
     [!CODE [concrt-basic-agent#12](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#12)]  
  
6.  Starten Sie den Agent, und warten Sie, bis er beendet wird.  
  
     [!CODE [concrt-basic-agent#13](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#13)]  
  
7.  Warten Sie, bis das `call`\-Objekt alle Daten empfangen hat, beenden Sie den Agent.  
  
     [!CODE [concrt-basic-agent#14](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#14)]  
  
8.  Überprüfen Sie die file\_reader\-Klasse auf Fehler.  Wenn kein Fehler aufgetreten ist, berechnen Sie die abschließende Adler\-32\-Prüfsumme, und geben Sie die Summe an der Konsole aus.  
  
     [!CODE [concrt-basic-agent#15](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#15)]  
  
 Das folgende Beispiel zeigt die vollständige BasicAgent.cpp\-Datei.  
  
 [!CODE [concrt-basic-agent#16](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-agent#16)]  
  
 \[[Nach oben](#top)\]  
  
## Beispieleingabe  
 Dies ist der Beispielinhalt der Eingabedatei text.txt:  
  
  **The quick brown fox**  
**jumps**  
**over the lazy dog**   
## Beispielausgabe  
 Wenn dieses Programm mit der Beispieleingabe verwendet wird, generiert es die folgende Ausgabe:  
  
  **Adler\-32 sum is fefb0d75**   
## Stabile Programmierung  
 Um gleichzeitigen Zugriff auf Datenmember zu verhindern, wird empfohlen, Methoden hinzufügen, die Arbeiten am `protected`\-Abschnitt oder am `private`\-Abschnitt der Klasse durchführen.  Fügen Sie dem `public`\-Abschnitt der Klasse nur Methoden hinzu, die Nachrichten an den Agent senden oder vom Agent empfangen.  
  
 Rufen Sie die [concurrency::agent::done](../Topic/agent::done%20Method.md)\-Methode immer auf, wenn der Agent in den abgeschlossenen Zustand verschoben werden soll.  Diese Methode wird in der Regel vor der Rückkehr von der `run`\-Methode aufgerufen.  
  
## Nächste Schritte  
 Ein weiteres Beispiel für eine agentbasierte Anwendung finden Sie unter [Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)   
 [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)   
 [Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)