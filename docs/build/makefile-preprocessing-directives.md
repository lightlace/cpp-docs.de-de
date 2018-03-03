---
title: "Makefile-Präprozessordirektiven | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs:
- C++
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1bc73a86b0772b13731aaf7ac4e2ef0760caa8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-directives"></a>Anweisungen für den Präprozessorlauf eines Makefiles
Vorverarbeitungsdirektiven sind nicht in der Groß-/Kleinschreibung beachtet. Das Ausrufungszeichen (!) muss am Anfang der Zeile angezeigt werden. 0 (null) oder mehrere Leerzeichen bzw. Tabstopps können nach dem Ausrufezeichen, für den Einzug angezeigt werden.  
  
 **! CMDSWITCHES**  
 {**+**&#124;  **-** }*Option*... Aktiviert die einzelnen *Option* aufgeführt, aktivieren oder deaktivieren. Leerzeichen oder Tabstopps müssen angezeigt werden, bevor Sie das + oder - Operator ist; keine können zwischen dem Operator angezeigt und die [option Buchstaben](../build/nmake-options.md). Buchstaben werden die Groß-/ Kleinschreibung nicht und ohne ein Schrägstrich (/) angegeben werden. Um usw. einige Optionen auf off zu aktivieren, verwenden Sie separate Spezifikationen von **! CMDSWITCHES**.  
  
 Nur/d / I, / n und/s in einem Makefile verwendet werden können. In der Datei Tools.ini dürfen sich alle Optionen außer/f "," / Help "," / nologo, / X, und /?. Änderungen, die in einem Beschreibungsblock angegeben werden nicht bis zum nächsten Beschreibung Blocks wirksam. Diese Direktive aktualisiert **MAKEFLAGS**; Änderungen werden während der Rekursion geerbt, wenn **MAKEFLAGS** angegeben ist.  
  
 **! Fehler beim***Text*   
 Zeigt *Text* in Fehler U1050 an, und hält NMAKE, selbst wenn/k, / I, **. IGNORIEREN**, **! CMDSWITCHES**, oder die Befehlsparameter Bindestrich (-) verwendet wird. Leerzeichen oder Tabstopps vor *Text* werden ignoriert.  
  
 **! Nachricht***Text*   
 Zeigt *Text* an die Standardausgabe. Leerzeichen oder Tabstopps vor *Text* werden ignoriert.  
  
 **! UMFASSEN**[  **\<** ] *Filename*[  **>** ]  
 Liest *Filename* als Makefile, fährt mit dem aktuellen Makefile. NMAKE sucht *Filename* zuerst im Verzeichnis angegebenen oder aktuellen dann rekursiv in Verzeichnissen aller an die übergeordnete Makefiles, klicken Sie dann, wenn *Filename* in spitzen Klammern eingeschlossen wird (\<>), in den Verzeichnissen, die gemäß der **INCLUDE** -Makro, das anfänglich auf die INCLUDE-Umgebungsvariable festgelegt ist. Wird zum Übergeben von **. SUFFIXE** Einstellungen **. WERTVOLLE**, und auf rekursive Makefiles Rückschlussregeln.  
  
 **! IF**  `constantexpression`  
 Anweisungen zwischen verarbeitet **! IF** und dem nächsten **! ELSE** oder `!ENDIF` Wenn `constantexpression` einen Wert ungleich null ergibt.  
  
 **! IFDEF***Macroname*   
 Anweisungen zwischen verarbeitet `!IFDEF` und dem nächsten **! ELSE** oder `!ENDIF` Wenn *Macroname* definiert ist. Ein null-Makro gilt definiert werden.  
  
 **! IFNDEF***Macroname*   
 Anweisungen zwischen verarbeitet **! IFNDEF** und dem nächsten **! ELSE** oder `!ENDIF` Wenn *Macroname* ist nicht definiert.  
  
 **! ELSE**[**IF** *KonstanterAusdruck* &#124; **IFDEF** *Macroname*&#124; **IFNDEF** *Macroname*]  
 Anweisungen zwischen verarbeitet **! ELSE** und dem nächsten `!ENDIF` Wenn die vorherige **! IF**, `!IFDEF`, oder **! IFNDEF** Anweisung nach 0 (null) ausgewertet. Die optionalen Schlüsselwörter bieten eine weitere Steuerung der vorverarbeitung.  
  
 **! ELSEIF**  
 Synonym für **! ElseIf**.  
  
 **! ELSEIFDEF**  
 Synonym für **! ELSE IFDEF**.  
  
 **! ELSEIFNDEF**  
 Synonym für **! ELSE IFNDEF**.  
  
 `!ENDIF`  
 Markiert das Ende einer **! IF**, `!IFDEF`, oder **! IFNDEF** Block. Beliebiger Text nach `!ENDIF` in derselben Zeile wird ignoriert.  
  
 **! UNDEF***Macroname*   
 Hebt die Definition *Macroname*.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorverarbeitung eines Makefiles](../build/makefile-preprocessing.md)