---
title: C-Laufzeitfehler R6024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6024
dev_langs:
- C++
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcdfee9da378415afe0b88fe6eed18ec8f570d4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302710"
---
# <a name="c-runtime-error-r6024"></a>C-Laufzeitfehler R6024
nicht genügend Speicherplatz für _onexit/Atexit-Tabelle  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da es ein Problem des internen Speichers hat. Dieser Fehler wird normalerweise verursacht werden, durch eine extrem wenig Arbeitsspeicher verfügbar, oder in seltenen Fällen einen Fehler im Programm oder eine Beschädigung der Visual C++-Bibliotheken, die verwendet werden.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Schließen Sie andere ausgeführte Programme, oder Neustart des Computers, um Arbeitsspeicher freizugeben.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren alle Kopien des verteilbaren Microsoft Visual C++.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler tritt auf, da es gab es keine "Erinnerung" für die `_onexit` oder `atexit` Funktion. Dieser Fehler wird durch eine Bedingung unzureichenden Arbeitsspeicher verursacht. Sie sollten vorab poolreservierung Puffer beim Starten der app, die beim Speichern von Benutzerdaten und eine fehlerfreie app ausführen unterstützen in Arbeitsspeichermangel zu beenden.