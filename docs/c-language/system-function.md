---
title: Systemfunktion
ms.date: 11/04/2016
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
ms.openlocfilehash: e37de4e084de6727cf2858117945fd162f6b0d63
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151220"
---
# <a name="system-function"></a>Systemfunktion

**ANSI 4.10.4.5** Die Inhalte und der Ausführmodus der Zeichenfolge durch die **system**-Funktion

Die **system**-Funktion führt einen internen Betriebssystembefehl oder eine EXE-, COM- (CMD in Windows NT) oder BAT-Datei aus einem C-Programm und nicht aus der Befehlszeile aus.

Die Systemfunktion durchsucht den Befehlsinterpreter, der in der Regel CMD.EXE im Windows NT-Betriebssystem oder COMMAND.COM in Windows ist. Die Systemfunktion gibt die Argumentzeichenfolge anschließend an den Befehlsinterpreter weiter.

Weitere Informationen finden Sie unter [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)
