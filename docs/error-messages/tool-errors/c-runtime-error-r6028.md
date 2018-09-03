---
title: C-Laufzeitfehler R6028 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6028
dev_langs:
- C++
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b978d1d9165fd48be9d0ce31aa72092fc660dbd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297822"
---
# <a name="c-runtime-error-r6028"></a>C-Laufzeitfehler R6028
Heap kann nicht initialisiert werden.  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da es ein Problem des internen Speichers hat. Es gibt viele mögliche Ursachen für diesen Fehler, aber häufig wird verursacht durch eine extrem wenig Arbeitsspeicher verfügbar, einen Fehler in der Anwendung oder durch fehlerhafte Hardware-Treiber.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Schließen Sie andere ausgeführte Programme, oder Neustart des Computers, um Arbeitsspeicher freizugeben.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Verwenden, wenn die Anwendung vor einer kürzlich durchgeführten Installationen von einer anderen app oder Treiber funktioniert, wurde die **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** So entfernen Sie die neue Anwendung oder Treiber, und versuchen Sie es erneut mit Ihrer app.  
> -   Überprüfen der der Website des Hardwareherstellers oder **Windows Update** in der **Systemsteuerung** Updates für Software und Treiber.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler tritt auf, wenn das Betriebssystem den Speicherpool für die Anwendung nicht erstellen konnte. Das heißt, CRT (C Runtime) hat die Win32-Funktion `HeapCreate` aufgerufen, die NULL zurückgibt und auf einen Fehler hinweist.  
  
 Wenn dieser Fehler während des Starts der App auftritt, kann das System die Heapanforderungen möglicherweise nicht erfüllen, da fehlerhafte Treiber geladen werden. Aktualisierte Treiber finden Sie unter Windows Update oder auf der Website des Hardwareherstellers.