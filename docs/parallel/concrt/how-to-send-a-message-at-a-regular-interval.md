---
title: "Gewusst wie: Senden einer Nachricht in regelm&#228;&#223;igen Intervallen | Microsoft Docs"
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
  - "timer-Klasse, Beispiel"
  - "Senden von Meldungen in regelmäßigen Intervallen [Concurrency Runtime]"
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Gewusst wie: Senden einer Nachricht in regelm&#228;&#223;igen Intervallen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie die Concurrency::[Timer-Klasse](../../parallel/concrt/reference/timer-class.md) zum Senden einer Nachricht in regelmäßigen Intervallen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird während eines längeren Vorgangs der Status mithilfe eines `timer`-Objekts angezeigt. Dieses Beispiel bindet der `timer` -Objekt an eine [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) Objekt. Das `call`-Objekt gibt in regelmäßigen Intervallen an der Konsole eine Statusanzeige aus. Die [Concurrency::timer::start](../Topic/timer::start%20Method.md) -Methode führt den Zeitgeber in einem separaten Kontext. Die `perform_lengthy_operation` -Funktion ruft die [Concurrency:: wait](../Topic/wait%20Function.md) Funktion main Kontext um einen zeitaufwändigen Vorgang zu simulieren.  
  
 [!CODE [concrt-report-progress#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-report-progress#1)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `report-progress.cpp` und dann den folgenden Befehl in einer Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc Report-progress.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)
