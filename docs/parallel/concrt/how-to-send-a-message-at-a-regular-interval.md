---
title: "Vorgehensweise: Senden einer Nachricht in regelmäßigen Abständen | Microsoft Docs"
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
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f12d9f8af028d1e2e1fc149eeb77181c2f6b1730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Gewusst wie: Senden einer Nachricht in regelmäßigen Intervallen
Dieses Beispiel zeigt, wie die Concurrency::[Timer-Klasse](../../parallel/concrt/reference/timer-class.md) zum Senden einer Nachricht in regelmäßigen Intervallen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird während eines längeren Vorgangs der Status mithilfe eines `timer`-Objekts angezeigt. Dieses Beispiel Links die `timer` -Objekt an eine [Call](../../parallel/concrt/reference/call-class.md) Objekt. Das `call`-Objekt gibt in regelmäßigen Intervallen an der Konsole eine Statusanzeige aus. Die [Concurrency::timer::start](reference/timer-class.md#start) -Methode führt den Zeitgeber in einem separaten Kontext. Die `perform_lengthy_operation` Funktionsaufrufe, die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) -Funktion im Hauptkontext um einen zeitaufwändigen Vorgang zu simulieren.  

  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `report-progress.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Report-progress.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)
