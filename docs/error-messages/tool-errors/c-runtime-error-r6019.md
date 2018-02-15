---
title: C-Laufzeitfehler R6019 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4ab7054bdce76aa1dd0b443993cfac8eeb8ecc7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="c-runtime-error-r6019"></a>C-Laufzeitfehler R6019
Console-Gerät kann nicht geöffnet  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da versucht wurde, Zugriff auf die Konsole, aber es wurde nicht über ausreichende Berechtigungen verfügen. Es gibt mehrere mögliche Ursachen für diesen Fehler ist in der Regel, da das Programm als Administrator ausgeführt werden muss oder ein Fehler im Programm vorhanden ist.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Führen Sie das Programm als Administrator an.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler tritt auf, da die app eine Konsole die Funktion aufgerufen, aber das Betriebssystem haben Zugriff auf die Konsole nicht erteilt. Mit Ausnahme von sind im Debugmodus, Konsolenfunktionen in der Regel nicht in Microsoft Store-apps zulässig. Falls Ihre app Administratorrechte zum Ausführen benötigt, stellen Sie sicher, dass es zum Ausführen als Administrator in der Standardeinstellung installiert wird.