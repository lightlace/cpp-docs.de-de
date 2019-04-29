---
title: Namensergänzung
ms.date: 04/22/2019
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: d1557f53a07a544ff4f9e5a63f905e6854fb74ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393154"
---
# <a name="name-decoration"></a>Namensergänzung

Namensergänzungen beziehen in der Regel auf C++-Benennungskonventionen, können jedoch auch auf eine Vielzahl von C-Fällen zutreffen. Standardmäßig verwendet C++ den Funktionsnamen, Parameter und den Rückgabetyp, um einen Linkernamen für die Funktion zu erstellen. Beachten Sie die folgende Funktionsdeklaration:

`void CALLTYPE test(void);`

In der folgenden Tabelle ist der Linkername für verschiedene Aufrufkonventionen dargestellt.

|Aufrufkonvention|`extern "C"` oder `.c` Datei|`.cpp`, `.cxx` oder `/TP`|
|------------------------|---------------------------|------------------------|
|C-Namenskonvention (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Schnelle aufrufbenennungskonvention (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|Standard aufrufen Benennungskonvention (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vector-aufrufbenennungskonvention (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

Verwendung `extern "C"` aufrufen, eine C-Funktion von C++. `extern "C"` Erzwingt die C-Benennungskonvention für nicht klassenbasierte C++ Funktionen. Achten Sie besonders vorsichtig bei Compilerschaltern **/TC** oder **/TP**, die den Compiler anweisen, die Dateierweiterung zu ignorieren und die Datei als C oder C++ kompiliert. Diese Optionen möglicherweise Linker-Namen, die Sie nicht erwarten.

Funktionsprototypen mit nicht übereinstimmenden Parametern können auch zu diesem Fehler führen. Namensergänzungen fügen die Parameter einer Funktion in den endgültigen ergänzten Funktionsnamen ein. Aufrufen einer Funktion mit den Parametertypen, die nicht mit denen in der Funktionsdeklaration übereinstimmen, kann ebenfalls LNK2001 verursacht.

Es gibt derzeit keine Standards für C++ Benennung zwischen compileranbietern oder sogar zwischen unterschiedlichen Versionen eines Compilers. Verknüpfen von Objektdateien, die von anderen Compilern kompiliert erzeugt möglicherweise nicht dasselbe Benennungsschema, und kann dazu führen, dass nicht aufgelöste externen.

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)