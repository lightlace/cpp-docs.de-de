---
title: C-Laufzeitfehler R6026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6026
dev_langs:
- C++
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7c8bea41b946db67ce24a52393d87873926f3f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298128"
---
# <a name="c-runtime-error-r6026"></a>C-Laufzeitfehler R6026
nicht genügend Speicherplatz für die Stdio-Initialisierung  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da es ein Problem des internen Speichers hat. Es gibt mehrere mögliche Ursachen für diesen Fehler, aber es wird normalerweise verursacht durch eine extrem wenig Arbeitsspeicher verfügbar. Er kann auch durch einen Bug in der app, eine Beschädigung der Visual C++-Bibliotheken, die verwendet oder von einem Treiber verursacht werden.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Schließen Sie andere ausgeführte Programme, oder Neustart des Computers, um Arbeitsspeicher freizugeben.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Verwenden, wenn die Anwendung vor einer kürzlich durchgeführten Installationen von einer anderen app oder Treiber funktioniert, wurde die **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** So entfernen Sie die neue Anwendung oder Treiber, und versuchen Sie es erneut mit Ihrer app.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren alle Kopien des verteilbaren Microsoft Visual C++.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler tritt auf, wenn nicht genügend Arbeitsspeicher verfügbar, um die standard-e/a--Unterstützung in der C-Laufzeit zu initialisieren. Dieser Fehler tritt gewöhnlich beim Starten der app. Stellen Sie sicher, dass Ihre app und die Treiber und Dlls, die es lädt den Heap beim Start nicht beschädigt.