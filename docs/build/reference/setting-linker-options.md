---
title: Festlegen von Linkeroptionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2fd99732c7f79b3c61ff5b31516b98a478ed4a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713075"
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