---
title: C-Laufzeitfehler R6016 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6016
dev_langs:
- C++
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 451ff01b201b110ac5f05140e3b8581f1a8c2e28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6016"></a>C-Laufzeitfehler R6016
Nicht genügend Speicher für Threaddaten  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da es ein Problem des internen Speichers hat. Es gibt viele mögliche Ursachen für diesen Fehler, aber häufig wird verursacht durch eine extrem wenig Arbeitsspeicher verfügbar, einen Fehler in der app oder durch einen Bug in einer Add-in oder eine Erweiterung, die von der app verwendet.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Schließen Sie andere ausgeführte Programme, oder Neustart des Computers, um Arbeitsspeicher freizugeben.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren der app.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** entfernen, reparieren oder neu installieren von Add-Ins oder Erweiterungen, die von der app verwendet.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler tritt auf, wenn das Programm nicht genügend Arbeitsspeicher vom Betriebssystem abgeschlossen eine [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) oder `_beginthreadex` Aufruf oder Thread wurde nicht vom lokaler Speicher initialisiert `_beginthread` oder `_beginthreadex`.  
  
 Beim Start eines neuen Threads muss die Bibliothek für diesen eine interne Datenbank anlegen. Wenn der vom Betriebssystem bereitgestellte Speicher nicht zum Erweitern dieser Datenbank ausreicht, wird der Thread nicht gestartet, und der Aufrufprozess wird angehalten. Das kann vorkommen, wenn durch den Prozess zu viele Threads erstellt wurden oder der threadlokale Speicher ausgeschöpft ist.  
  
 Es wird empfohlen, eine ausführbare Datei, die die C-Laufzeitbibliothek (CRT) aufruft, sollte `_beginthreadex` für Threaderstellung statt der Windows-API `CreateThread`. `_beginthreadex` initialisiert den internen statischen Speicher, der von vielen CRT-Funktionen im lokalen Threadspeicher verwendet wird. Wenn Sie zur Erstellung eines Threads die `CreateThread`-Funktion verwenden, beendet das CRT den Prozess beim Aufruf einer CRT-Funktion, die initialisierten internen statischen Speicher benötigt, möglicherweise mit R6016.