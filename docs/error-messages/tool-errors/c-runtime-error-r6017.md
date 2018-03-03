---
title: C-Laufzeitfehler R6017 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57345feed2044683a1d5fd2a6ee7d14c412a827d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6017"></a>C-Laufzeitfehler R6017
Unerwarteter multithread-Lock-Fehler  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Es gibt mehrere mögliche Ursachen für diesen Fehler wird häufig durch einen Fehler in der app-Code verursacht.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Der Prozess empfangen einen unerwarteten Fehler beim Versuch, eine C-Laufzeit multithread-Sperre auf eine Systemressource zugreifen. Dieser Fehler tritt gewöhnlich auf, wenn der Prozess versehentlich die Common Language Runtime-Heap-Daten ändert. Es kann jedoch auch durch einen internen Fehler in der Common Language runtimebibliothek oder ein Betriebssystem-Code verursacht werden.  
  
 Um dieses Problem zu beheben, suchen Sie nach Heap-Beschädigung-Fehler im Code. Weitere Informationen und Beispiele finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Überprüfen Sie, dass Sie die neuesten verteilbaren Komponenten für Ihre app-Bereitstellung verwenden. Informationen finden Sie unter [Bereitstellung in Visual C++](../../ide/deployment-in-visual-cpp.md).