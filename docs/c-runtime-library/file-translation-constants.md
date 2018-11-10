---
title: Dateiübersetzungskonstanten
ms.date: 11/04/2016
f1_keywords:
- c.constants.file
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
ms.openlocfilehash: d98a74c820023ac8684f54413c0e81c58eba7b0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443289"
---
# <a name="file-translation-constants"></a>Dateiübersetzungskonstanten

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Hinweise

Diese Konstanten geben den Modus der Übersetzung an (**„b“** oder **„t“**). Der Modus ist in der Zeichenfolge enthalten, die den Typ des Zugriffs angibt (**„r“**, **„w“**, **„a“**, **„r+“**, **„w+“**, **„a+“**).

Die Übersetzungsmodi lauten wie folgt:

- **t**

   Öffnet im Textmodus (übersetzt). Im Textmodus werden Wagenrücklauf-/Zeilenvorschub-Kombinationen (CR-LF) bei der Eingabe in einzelne Zeilenvorschübe (LF) übersetzt. LF-Zeichen werden bei der Ausgabe in CR-LF-Kombinationen übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In den Dateien, die für das Lesen oder Lesen/Schreiben geöffnet sind, überprüft `fopen` die Datei auf STRG+Z am Dateiende, und entfernt sofern möglich die Markierung. Dies geschieht, da ein Verwenden der Funktionen `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit STRG + Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht ordnungsgemäß verhält.

   > [!NOTE]
   > Die **t**-Option ist nicht Teil des ANSI-Standards für `fopen` und `freopen`. Sie ist eine Microsoft-Erweiterung, die bei einer gewünschten ANSI-Portabilität nicht verwendet werden sollte.

- **b**

   Öffnet im binären (nicht übersetzten) Modus. Die oben genannten Übersetzungen werden unterdrückt.

Wenn **t** oder **b** nicht in *mode* angegeben ist, wird der Übersetzungsmodus durch die Standardmodusvariable [_fmode](../c-runtime-library/fmode.md) definiert. Weitere Informationen zur Verwendung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="see-also"></a>Siehe auch

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)