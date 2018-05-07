---
title: C-Laufzeitfehler R6027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6027
dev_langs:
- C++
helpviewer_keywords:
- R6027
ms.assetid: c06a62b3-08d9-4bf5-bcad-8340ec552f69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc38d664a6c9e2e2be0c360709ed6b39b1014b05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6027"></a>C-Laufzeitfehler R6027
nicht genügend Speicherplatz für Lowio-Initialisierung.  
  
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
  
 Dieser Fehler tritt auf, wenn nicht genug freier Arbeitsspeicher für die Low-Level e/a-Unterstützung in der C-Laufzeit zu initialisieren. Dieser Fehler tritt gewöhnlich beim Starten der app. Stellen Sie sicher, dass Ihre app und die Treiber und Dlls, die es lädt den Heap beim Start nicht beschädigt.