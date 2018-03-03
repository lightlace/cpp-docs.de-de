---
title: 'Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung | Microsoft Docs'
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
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a49c8deb9185b024dfcca977ab229bf594e05101
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-an-agent-based-application"></a>Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung
In diesem Thema wird die Erstellung einer einfachen agentbasierten Anwendung beschrieben. In dieser exemplarischen Vorgehensweise können Sie einen Agent erstellen, der Daten asynchron aus einer Textdatei ausliest. Die Anwendung berechnet die Prüfsumme des Inhalts dieser Datei mithilfe des Adler-32-Prüfsummenalgorithmus.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise sollten Sie die folgenden Themen lesen:  
  
- [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)  
  
- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)  
  
- [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Abschnitte  
 Mit dieser exemplarischen Vorgehensweise wird die Durchführung der folgenden Aufgaben beschrieben:  
  
- [Erstellen der Konsolenanwendung](#createapplication)  
  
- [Erstellen der File_reader-Klasse](#createagentclass)  
  
- [Verwenden der File_reader-Klasse in der Anwendung](#useagentclass)  
  
##  <a name="createapplication"></a>Erstellen der Konsolenanwendung  
 In diesem Abschnitt wird die Erstellung einer Visual C++-Konsolenanwendung beschrieben, die auf die vom Programm verwendeten Headerdateien verweist.  
  
#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>So erstellen Sie eine Visual C++-Anwendung mit dem Win32-Anwendungs-Assistenten  
  
1.  Auf der **Datei** Menü klicken Sie auf **neu**, und klicken Sie dann auf **Projekt** zum Anzeigen der **neues Projekt** (Dialogfeld).  
  
2.  In der **neues Projekt** wählen Sie im Dialogfeld die **Visual C++** Knoten in der **-Projekttypen** und wählen Sie dann **Win32-Konsolenanwendung** in der **Vorlagen** Bereich. Geben Sie einen Namen für das Projekt, z. B. `BasicAgent`, und klicken Sie dann auf **OK** zum Anzeigen der **Win32-Anwendungs-Assistenten**.  
  
3.  In der **Win32-Anwendungs-Assistenten** (Dialogfeld), klicken Sie auf **Fertig stellen**.  
  
4.  Fügen Sie in der Datei stdafx.h den folgenden Code hinzu.  
  
 [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]  
  
     Die Headerdatei agents.h enthält die Funktionalität der [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) Klasse.  
  
5.  Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Um die Anwendung zu erstellen. die **erstellen** Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung, indem Sie auf **Debuggen** auf die **Debuggen** Menü.  
  
 [[Nach oben](#top)]  
  
##  <a name="createagentclass"></a>Erstellen der File_reader-Klasse  
 In diesem Abschnitt wird die Erstellung der `file_reader`-Klasse beschrieben. Die Runtime plant jeden Agent so, dass er Arbeiten im eigenen Kontext ausführt. Daher können Sie einen Agent erstellen, der Arbeiten synchron ausführt, aber asynchron mit anderen Komponenten interagiert. Die `file_reader`-Klasse liest Daten aus einer angegebenen Eingabedatei aus und sendet Daten aus dieser Datei an eine angegebene Zielkomponente.  
  
#### <a name="to-create-the-filereader-class"></a>So erstellen Sie die file_reader-Klasse  
  
1.  Fügen Sie dem Projekt eine neue C++-Headerdatei hinzu. Dazu, mit der Maustaste die **Headerdateien** Knoten **Projektmappen-Explorer**, klicken Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element**. In der **Vorlagen** klicken Sie im Bereich **Headerdatei (. h)**. In der **neues Element hinzufügen** Geben Sie im Dialogfeld `file_reader.h` in der **Namen** Feld, und klicken Sie dann auf **hinzufügen**.  
  
2.  Fügen Sie in der Datei file_reader.h den folgenden Code hinzu.  
  
 [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  Erstellen Sie in der Datei file_reader.h eine Klasse mit dem Namen `file_reader`, die von `agent` abgeleitet wird.  
  
 [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  Fügen Sie dem `private`-Abschnitt der Klasse die folgenden Datenmember hinzu.  
  
 [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]  
  
     Der `_file_name`-Member ist der Name der Datei, die vom Agent ausgelesen wird. Die `_target` Member ist ein [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) Objekt, das der Agent den Inhalt der Datei, schreibt. Der `_error`-Member speichert alle Fehler, die während der Lebensdauer des Agents auftreten.  
  
5.  Fügen Sie dem `file_reader`-Abschnitt der  `public`-Klasse den folgenden Code für die `file_reader`-Konstruktoren hinzu.  
  
 [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]  
  
     Mit jeder Konstruktorüberladung werden die `file_reader`-Datenmember festgelegt. Mit der zweiten und dritten Konstruktorüberladung wird es der Anwendung ermöglicht, mit dem Agent einen bestimmten Planer zu verwenden. Bei der ersten Überladung wird der Standardplaner mit dem Agent verwendet.  
  
6.  Fügen Sie dem public-Abschnitt der `get_error`-Klasse die `file_reader`-Methode hinzu.  
  
 [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]  
  
     Die `get_error`-Methode ruft alle Fehler ab, die während der Lebensdauer des Agents auftreten.  
  

7.  Implementieren der [Concurrency::agent::run](reference/agent-class.md#run) Methode in der `protected` -Abschnitt der Klasse.  

  
 [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]  
  
Die `run`-Methode öffnet die Datei und liest Daten aus. Die `run`-Methode erfasst mithilfe der Ausnahmebehandlung alle Fehler, die während der Dateiverarbeitung auftreten.  
  
   Jedes Mal, diese Methode Daten aus der Datei liest, ruft der [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) Funktion, um diese Daten an den Zielpuffer zu senden. Sie sendet die leere Zeichenfolge an den Zielpuffer, um so das Ende der Verarbeitung anzugeben.  

  
 Im folgenden Beispiel wird der vollständige Inhalt der Datei file_reader.h dargestellt.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]  
  
 [[Nach oben](#top)]  
  
##  <a name="useagentclass"></a>Verwenden der File_reader-Klasse in der Anwendung  
 In diesem Abschnitt wird beschrieben, wie mithilfe der `file_reader`-Klasse der Inhalt einer Textdatei gelesen wird. Außerdem wird gezeigt, wie zum Erstellen einer [Call](../../parallel/concrt/reference/call-class.md) Objekt, das diese Dateidaten empfängt und die Adler-32-Prüfsumme berechnet.  
  
#### <a name="to-use-the-filereader-class-in-your-application"></a>So verwenden Sie die file_reader-Klasse in der Anwendung  
  
1.  Fügen Sie in der Datei BasicAgent.cpp die folgende `#include`-Anweisung hinzu.  
  
 [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  Fügen Sie in der Datei BasicAgent.cpp die folgenden `using`-Direktiven hinzu.  
  
 [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  In der `_tmain` funktionieren, erstellen Sie eine [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt, das das Ende der Verarbeitung signalisiert.  
  
 [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  Erstellen Sie ein `call`-Objekt, das beim Empfang von Daten die Prüfsumme aktualisiert.  
  
 [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     Dieses `call`-Objekt legt darüber hinaus auch das `event`-Objekt fest, wenn es die leere Zeichenfolge empfängt, um das Ende der Verarbeitung zu signalisieren.  
  
5.  Erstellen Sie ein `file_reader`-Objekt, das aus der Datei test.txt ausliest und den Inhalt dieser Datei in das `call`-Objekt schreibt.  
  
 [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  Starten Sie den Agent, und warten Sie, bis er beendet wird.  
  
 [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  Warten Sie, bis das `call`-Objekt alle Daten empfangen hat, beenden Sie den Agent.  
  
 [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  Überprüfen Sie die file_reader-Klasse auf Fehler. Wenn kein Fehler aufgetreten ist, berechnen Sie die abschließende Adler-32-Prüfsumme, und geben Sie die Summe an der Konsole aus.  
  
 [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 Das folgende Beispiel zeigt die vollständige BasicAgent.cpp-Datei.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 [[Nach oben](#top)]  
  
## <a name="sample-input"></a>Beispieleingabe  
 Dies ist der Beispielinhalt der Eingabedatei text.txt:  
  
```Output  
The quick brown fox  
jumps  
over the lazy dog  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
 Wenn dieses Programm mit der Beispieleingabe verwendet wird, generiert es die folgende Ausgabe:  
  
```Output  
Adler-32 sum is fefb0d75  
```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Um gleichzeitigen Zugriff auf Datenmember zu verhindern, wird empfohlen, Methoden hinzufügen, die Arbeiten am `protected`-Abschnitt oder am `private`-Abschnitt der Klasse durchführen. Fügen Sie dem `public`-Abschnitt der Klasse nur Methoden hinzu, die Nachrichten an den Agent senden oder vom Agent empfangen.  
  

 Rufen Sie immer die [Concurrency:: Agent:: Fertig](reference/agent-class.md#done) Methode, um den Agent auf den abgeschlossenen Zustand zu verschieben. Diese Methode wird in der Regel vor der Rückkehr von der `run`-Methode aufgerufen.  

  
## <a name="next-steps"></a>Nächste Schritte  
 Ein weiteres Beispiel einer agentbasierten Anwendung finden Sie unter [Exemplarische Vorgehensweise: Verhindern von Deadlocks mit Join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)   
 [Strukturen für Synchronisierungsdaten](../../parallel/concrt/synchronization-data-structures.md)   
 [Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

