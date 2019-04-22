---
title: Anweisungen für den Präprozessorlauf eines Makefiles
ms.date: 06/14/2018
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
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
ms.openlocfilehash: 0945d0e1c149b7e1ab31b0dbbd5003f8b15a1e4d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825493"
---
# <a name="makefile-preprocessing-directives"></a>Anweisungen für den Präprozessorlauf eines Makefiles

Vorverarbeitungsdirektiven sind nicht in der Groß-/Kleinschreibung beachtet. Das Ausrufungszeichen (!) muss am Anfang der Zeile angezeigt werden. 0 (null) oder mehr Leerzeichen oder Tabstopps können nach dem Ausrufezeichen, für den Einzug angezeigt werden.

- **!CMDSWITCHES** {**+** &#124; **-**}*option* ...

   Aktiviert die einzelnen *Option* aufgeführt, aktivieren oder deaktivieren. Leerzeichen oder Tabstopps müssen angezeigt werden, bevor Sie das + oder - Operator ist; keiner enthalten sein zwischen dem Operator und die [option Buchstaben](nmake-options.md). Buchstaben werden Groß-/ Kleinschreibung nicht und werden ohne einen Schrägstrich (/) angegeben. Um auf einige Optionen und andere aus aktivieren möchten, verwenden Sie separate Spezifikationen von **! CMDSWITCHES**.

   Nur/d / ich/n und "/ s" kann in einem Makefile verwendet werden. In der Datei Tools.ini dürfen sich alle Optionen außer/f "," / Help "," / nologo, / X und /?. Änderungen, die in einem Beschreibungsblock angegeben werden nicht bis zum nächsten Beschreibung Blocks wirksam. Diese Direktive aktualisiert **MAKEFLAGS**; Änderungen werden während der Rekursion geerbt, wenn **MAKEFLAGS** angegeben ist.

- **! Fehler** *Text*

   Zeigt *Text* in Fehler U1050 an, und hält NMAKE, selbst wenn/k, /, **. IGNORIEREN Sie**, **! CMDSWITCHES**, oder dem Bindestrich (-) Befehlsmodifizierer verwendet wird. Leerzeichen oder vor dem Registerkarten *Text* werden ignoriert.

- **! Nachricht** *Text*

   Zeigt *Text* an die Standardausgabe. Leerzeichen oder vor dem Registerkarten *Text* werden ignoriert.

- **! UMFASSEN** [ **\<** ] *Filename* [ **>** ]

   Liest *Filename* als Makefile, klicken Sie dann mit dem aktuellen Makefile zu fort. NMAKE sucht *Filename* zuerst im Verzeichnis angegebenen oder aktuellen dann rekursiv in den Verzeichnissen aller an die übergeordnete Makefiles, klicken Sie dann, wenn *Filename* von spitzen Klammern eingeschlossen (\<>), in den Verzeichnissen durch die **INCLUDE** Makro, das anfänglich auf die INCLUDE-Umgebungsvariable festgelegt ist. Wird zum Übergeben von **. SUFFIXE** Einstellungen **. WERTVOLLE**, und Rückschlussregeln zum rekursiven Makefiles.

- **!IF** *constant_expression*

   Verarbeitet die Anweisungen zwischen **! IF** und dem nächsten **! ANDERE** oder **! ENDIF** Wenn *Constant_expression* einen Wert ungleich null ergibt.

- **! IFDEF** *Makroname*

   Verarbeitet die Anweisungen zwischen **! IFDEF** und dem nächsten **! ANDERE** oder **! ENDIF** Wenn *Macroname* definiert ist. Ein null-Makro gilt definiert werden.

- **! IFNDEF** *Makroname*

   Verarbeitet die Anweisungen zwischen **! IFNDEF** und dem nächsten **! ANDERE** oder **! ENDIF** Wenn *Macroname* ist nicht definiert.

- **!ELSE** [**IF** *constant_expression* &#124; **IFDEF** *macroname* &#124; **IFNDEF** *macroname*]

   Verarbeitet die Anweisungen zwischen **! ANDERE** und dem nächsten **! ENDIF** Wenn der vorherige **! IF**, **! IFDEF**, oder **! IFNDEF** Anweisung 0 (null) ausgewertet. Die optionalen Schlüsselwörter bieten eine weitere Steuerung der vorverarbeitung.

- **!ELSEIF**

   Synonym für **! ElseIf**.

- **!ELSEIFDEF**

   Synonym für **! ANDERE IFDEF**.

- **!ELSEIFNDEF**

   Synonym für **! ANDERE IFNDEF**.

- **!ENDIF**

   Markiert das Ende einer **! IF**, **! IFDEF**, oder **! IFNDEF** Block. Sämtlicher Text nach **! ENDIF** in der gleichen Zeile wird ignoriert.

- **! UNDEF** *Makroname*

   Hebt die Definierung *Macroname*.

## <a name="see-also"></a>Siehe auch

- [Vorverarbeitung eines Makefiles](makefile-preprocessing.md)