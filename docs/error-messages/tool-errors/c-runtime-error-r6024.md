---
title: C-Laufzeitfehler R6024 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6024
dev_langs: C++
helpviewer_keywords: R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d032bbcb6e28d78f5e43b9c12499c6d47ca0310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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