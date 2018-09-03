---
title: C-Laufzeitfehler R6008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6008
dev_langs:
- C++
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d32734850c58b64694e96c3a27b759131e6c5ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299876"
---
# <a name="c-runtime-error-r6008"></a>C-Laufzeitfehler R6008
nicht genügend Speicherplatz für Argumente  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da es ein Problem des internen Speichers hat. Es gibt mehrere mögliche Ursachen für diesen Fehler, aber es ist häufig eine extrem wenig Arbeitsspeicher verfügbar, zu viel Arbeitsspeicher von Umgebungsvariablen oder einen Fehler in der Anwendung ausgeführte zurückzuführen.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Schließen Sie andere ausgeführte Programme, oder Neustart des Computers, um Arbeitsspeicher freizugeben.  
> -   Verringern Sie die Anzahl und Größe von Befehlszeilenargumenten, um die app an.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Es war zwar genügend Arbeitsspeicher zum Laden des Programms jedoch nicht genügend Arbeitsspeicher zum Erstellen der **Argv** Array. Dies kann durch extrem Speichermangel oder durch ungewöhnlich umfangreich Befehlszeilen oder Umgebung Variable Auslastung verursacht werden. Betrachten Sie eine der folgenden Lösungen:  
  
-   Erhöhen Sie die Menge an Arbeitsspeicher für das Programm verfügbar.  
  
-   Reduzieren Sie die Anzahl und Größe von Befehlszeilenargumenten.  
  
-   Reduzieren der Größe der Umgebung durch das Entfernen unnötiger Variablen an.