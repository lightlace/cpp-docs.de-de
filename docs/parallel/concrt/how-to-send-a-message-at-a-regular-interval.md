---
title: 'Vorgehensweise: Senden einer Nachricht in regelmäßigen Abständen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6903a7ec6b833f7591afe79dc91d453b3905cc79
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705249"
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
