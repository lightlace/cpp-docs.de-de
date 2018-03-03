---
title: C-Laufzeitfehler R6008 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6008
dev_langs:
- C++
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86b64f97768359b95d2c5e2003cfb5b95a2aac71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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