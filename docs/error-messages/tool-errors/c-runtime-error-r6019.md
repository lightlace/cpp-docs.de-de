---
title: C-Laufzeitfehler R6019 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6019
dev_langs: C++
helpviewer_keywords: R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 32b2b2f29b1b426ab67f089ae7a54a9730f16535
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
 Dieser Fehler tritt auf, da die app eine Konsole die Funktion aufgerufen, aber das Betriebssystem haben Zugriff auf die Konsole nicht erteilt. Mit Ausnahme von sind im Debugmodus, Konsolenfunktionen in der Regel nicht in Windows Store-apps zulässig. Falls Ihre app Administratorrechte zum Ausführen benötigt, stellen Sie sicher, dass es zum Ausführen als Administrator in der Standardeinstellung installiert wird.