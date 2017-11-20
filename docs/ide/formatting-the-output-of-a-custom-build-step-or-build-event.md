---
title: Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder Buildereignisses | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 189f18f5d8944fc61635b5aa83522e5a89a3a100
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses
Wenn die Ausgabe eines benutzerdefinierten Buildschritts oder Buildereignisses ordnungsgemäß formatiert ist, erhalten Benutzer die folgenden Vorteile:  
  
-   Warnungen und Fehler im gezählt werden, die **Ausgabe** Fenster.  
  
-   Ausgabe wird angezeigt, der **Aufgabenliste** Fenster.  
  
-   Durch Klicken auf die Ausgabe in die **Ausgabe** Fenster werden im entsprechende Thema angezeigt.  
  
-   F1-Operationen sind aktiviert, der **Aufgabenliste** Fenster oder **Ausgabe** Fenster.  
  
 Das Format der Ausgabe sollte wie folgt sein:  
  
 {*Filename* (*Zeilennr* [, *Spalte #*]) &#124; *Programmname*} **:**  
  
 [*einen beschreibenden Text*] {**Fehler** &#124; **Warnung**} *Code ###***:***lokalisierbare Zeichenfolge*  
  
 [ *einen beschreibenden Text* ]  
  
 Ort:  
  
-   {*eine* &#124; *b*} gibt eine Auswahl von entweder *eine* oder *b*.  
  
-   [`ccc`] ist eine optionale Zeichenfolge oder ein Parameter.  
  
 Zum Beispiel:  
  
 "C:"\\*sourcefile.cpp*(134): Fehler C2143: Syntaxfehler: Fehlender ";" vor "}"  
  
 LINK: Schwerwiegender Fehler LNK1104: Öffnen der Datei "*somelib.lib*"  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)