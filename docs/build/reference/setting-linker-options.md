---
title: Festlegen von Linkeroptionen
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
ms.openlocfilehash: 5b885ad5c86bc59029fc6a3a60ccee385703ab2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508939"
---
# <a name="setting-linker-options"></a>Festlegen von Linkeroptionen

Optionen des Linkers können innerhalb oder außerhalb der Entwicklungsumgebung festgelegt werden. Das Thema für jede-Linkeroption wird erläutert, wie sie in der Entwicklungsumgebung eingestellt werden kann. Finden Sie unter [Optionen des Linkers](../../build/reference/linker-options.md) für eine vollständige Liste.

Wenn Sie den LINK außerhalb der Entwicklungsumgebung ausführen, können Sie die Eingabe auf einen oder mehrere Arten angeben:

- Auf der [über die Befehlszeile](../../build/reference/linker-command-line-syntax.md)

- Mithilfe von [Befehlsdateien](../../build/reference/link-command-files.md)

- In [Umgebungsvariablen](../../build/reference/link-environment-variables.md)

LINK zuerst Prozesse angegebenen Optionen in der LINK-Umgebungsvariablen, gefolgt von den Optionen in der Reihenfolge, die sie in der Befehlszeile angegeben sind und in Befehlsdateien. Wenn Sie eine Option mit verschiedenen Argumenten wiederholt wird, hat der letzte Suchvorgang verarbeitet Vorrang vor.

Optionen gelten für die gesamte Build; keine Optionen können für bestimmte Eingabedateien angewendet werden.

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)