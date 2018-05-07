---
title: C-Laufzeitfehler R6018 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6018
dev_langs:
- C++
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4946e3a8341963ee1a1ca2c3ad65d64cfbad8080
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6018"></a>C-Laufzeitfehler R6018
unerwarteter Heapfehler  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Es gibt mehrere mögliche Ursachen für diesen Fehler wird häufig durch einen Fehler in der app-Code verursacht.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Das Programm wird festgestellt, dass einen unerwarteten Fehler ein Speicher-Management-Vorgang.  
  
 Dieser Fehler tritt gewöhnlich auf, wenn das Programm unbeabsichtigt die Laufzeit-Heapdaten ändert. Es kann jedoch auch durch einen internen Fehler in der Common Language Runtime oder einen Betriebssystem-Code verursacht werden.  
  
 Um dieses Problem zu beheben, suchen Sie nach Heap-Beschädigung-Fehler im Code. Weitere Informationen und Beispiele finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Überprüfen Sie, dass Sie die neuesten verteilbaren Komponenten für Ihre app-Bereitstellung verwenden. Informationen finden Sie unter [Bereitstellung in Visual C++](../../ide/deployment-in-visual-cpp.md).