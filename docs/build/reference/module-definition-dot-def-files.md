---
title: Moduldefinitionsdateien (.Def)
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: 0047f24722644cd9a68bbbf827ced26ad085d4c1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812238"
---
# <a name="module-definition-def-files"></a>Moduldefinitionsdateien (.Def)

Moduldefinitionsdateien (.def) Geben Sie den Linker mit Informationen zu Exporten, Attribute und andere Informationen zum Programm verknüpft werden kann. Eine DEF-Datei ist besonders hilfreich, wenn Sie eine DLL-Datei zu erstellen. Da gibt es [MSVC-Linkeroptionen](linker-options.md) verwendet werden können statt moduldefinitionsanweisungen, DEF-Dateien sind im Allgemeinen nicht erforderlich. Sie können auch [__declspec(dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md) als eine Möglichkeit, geben Sie auf exportierte Funktionen.

Sie können eine DEF-Datei aufrufen, während der Linkerphase ein, mit der [/DEF (Moduldefinitionsdatei festlegen)](def-specify-module-definition-file.md) -Linkeroption.

Wenn Sie eine .exe-Datei, die über keine Exportdaten verfügt erstellen, veranlasst der über eine DEF-Datei die größeren und langsameren laden Ihre Ausgabe-Datei aus.

Ein Beispiel finden Sie unter [exportieren aus einer DLL mithilfe von DEF-Dateien](../exporting-from-a-dll-using-def-files.md).

Finden Sie unter den folgenden Abschnitten Weitere Informationen:

- [Regeln für Moduldefinitionsanweisungen](rules-for-module-definition-statements.md)

- [EXPORTE](exports.md)

- [HEAPSIZE](heapsize.md)

- [BIBLIOTHEK](library.md)

- [NAME](name-c-cpp.md)

- [ABSCHNITTE](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [STUB](stub.md)

- [VERSION](version-c-cpp.md)

- [Reservierte Wörter](reserved-words.md)

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
