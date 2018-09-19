---
title: Umgebungsnamen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4df255959ab1c60a5ccaeb9c4389cbcbdc56368b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081415"
---
# <a name="environment-names"></a>Umgebungsnamen

**ANSI 4.10.4.4** Der Satz von Umgebungsnamen und die Methode zum Ändern der Umgebungsliste, die von der [getenv](../c-runtime-library/reference/getenv-wgetenv.md)-Funktion verwendet wird

Der Satz der Umgebungsnamen ist unbegrenzt.

Um die Umgebungsvariablen in einem C-Programm zu ändern, rufen Sie die [_putenv](../c-runtime-library/reference/putenv-wputenv.md)-Funktion auf. Um Umgebungsvariablen über die Befehlszeile in Windows zu ändern, verwenden Sie den SET-Befehl (z. B. SET LIB = D:\ LIBS).

Die Umgebungsvariablen, die aus einem C-Programm festgelegt werden, existieren nur, solange ihre Hostkopie der Befehlsshell des Betriebssystems ausgeführt wird (CMD.EXE oder COMMAND.COM). Beispiel: Die Zeile

```
system( SET LIB = D:\LIBS );
```

würde eine Kopie der Befehlsshell (CMD.EXE) ausführen, die Umgebungsvariable LIB festlegen und zum C-Programm zurückkehren, wobei die sekundäre Kopie von CMD.EXE beendet wird. Durch das Beenden dieser Kopie der CMD.EXE wird die temporäre Umgebungsvariable LIB entfernt.

Entsprechend bleiben Änderungen, die von der `_putenv`-Funktion vorgenommen werden, nur bis zum Beenden des Programms erhalten.

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)