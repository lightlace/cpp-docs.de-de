---
title: Moduldefinitionsdateien (.Def)
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: a882d71e76b961fefb7059bee8634507f12f7986
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460436"
---
# <a name="module-definition-def-files"></a>Moduldefinitionsdateien (.Def)

Moduldefinitionsdateien (.def) Geben Sie den Linker mit Informationen zu Exporten, Attribute und andere Informationen zum Programm verknüpft werden kann. Eine DEF-Datei ist besonders hilfreich, wenn Sie eine DLL-Datei zu erstellen. Da gibt es [Optionen des Linkers](../../build/reference/linker-options.md) verwendet werden können statt moduldefinitionsanweisungen, DEF-Dateien sind im Allgemeinen nicht erforderlich. Sie können auch [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) als eine Möglichkeit, geben Sie auf exportierte Funktionen.

Sie können eine DEF-Datei aufrufen, während der Linkerphase ein, mit der [/DEF (Moduldefinitionsdatei festlegen)](../../build/reference/def-specify-module-definition-file.md) -Linkeroption.

Wenn Sie eine .exe-Datei, die über keine Exportdaten verfügt erstellen, veranlasst der über eine DEF-Datei die größeren und langsameren laden Ihre Ausgabe-Datei aus.

Ein Beispiel finden Sie unter [exportieren aus einer DLL mithilfe von DEF-Dateien](../../build/exporting-from-a-dll-using-def-files.md).

Finden Sie unter den folgenden Abschnitten Weitere Informationen:

- [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)

- [EXPORTE](../../build/reference/exports.md)

- [HEAPSIZE](../../build/reference/heapsize.md)

- [BIBLIOTHEK](../../build/reference/library.md)

- [NAME](../../build/reference/name-c-cpp.md)

- [ABSCHNITTE](../../build/reference/sections-c-cpp.md)

- [STACKSIZE](../../build/reference/stacksize.md)

- [STUB](../../build/reference/stub.md)

- [VERSION](../../build/reference/version-c-cpp.md)

- [Reservierte Wörter](../../build/reference/reserved-words.md)

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)