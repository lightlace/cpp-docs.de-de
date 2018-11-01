---
title: Festlegen von Compileroptionen
ms.date: 11/04/2016
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
ms.openlocfilehash: 62a6c7913a088f9b986a09b205e4fb9bb350581a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602188"
---
# <a name="setting-compiler-options"></a>Festlegen von Compileroptionen

C- und C++-Compileroptionen können entweder in der Entwicklungsumgebung oder über die Befehlszeile festgelegt werden.

## <a name="in-the-development-environment"></a>In der Entwicklungsumgebung

Sie können festlegen der Compileroptionen für jedes Projekt in der **Eigenschaftenseiten** Dialogfeld. Wählen Sie im linken Bereich **Konfigurationseigenschaften**, **C/C++-** und wählen Sie dann die Kategorie der Compiler-Option. In den Themen zu den einzelnen Compileroptionen wird erläutert, wo die jeweilige Option in der Entwicklungsumgebung zu finden ist und wie sie eingestellt werden kann. Finden Sie unter [Compileroptionen](../../build/reference/compiler-options.md) für eine vollständige Liste.

## <a name="outside-the-development-environment"></a>Außerhalb der Entwicklungsumgebung

Sie können die Optionen für den Compiler (CL.exe) an folgenden Stellen festlegen:

- [In der Befehlszeile](../../build/reference/compiler-command-line-syntax.md)

- [In Befehlsdateien](../../build/reference/cl-command-files.md)

- [In der CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md)

Die in der CL-Umgebungsvariablen festgelegten Optionen werden bei jedem Aufrufen von CL.EXE verwendet. Wenn eine Befehlsdatei in der CL-Umgebungsvariablen oder in der Befehlszeile angegeben wird, werden die in der Befehlsdatei festgelegten Optionen verwendet. Anders als in der Befehlszeile oder in der CL-Umgebungsvariablen können Sie in einer Befehlsdatei mehrzeilige Optionen und Dateinamen verwenden.

Compileroptionen werden "von links nach rechts" verarbeitet. Wird ein Konflikt erkannt, überwiegt die letzte Option (ganz rechts). Die CL-Umgebungsvariable wird vor der Befehlszeile verarbeitet. Sollte es also zu Konflikten zwischen CL und der Befehlszeile kommen, so hat die Befehlszeile Vorrang.

## <a name="additional-compiler-topics"></a>Weitere Themen zum Compiler

- [Schnelle Kompilierung](../../build/reference/fast-compilation.md)

- [CL: Starten des Linkers](../../build/reference/cl-invokes-the-linker.md)

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)