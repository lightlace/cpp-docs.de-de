---
title: Benennen Sie die Dekoration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa493a886509a85cc45c14f003ff07886c435280
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036032"
---
# <a name="name-decoration"></a>Namensergänzung

Namensergänzungen beziehen in der Regel auf C++-Benennungskonventionen, können jedoch auch auf eine Vielzahl von C-Fällen zutreffen. Standardmäßig verwendet C++ den Funktionsnamen, Parameter und den Rückgabetyp, um einen Linkernamen für die Funktion zu erstellen. Nehmen wir einmal die folgende Funktion:

```
void CALLTYPE test(void)
```

In der folgenden Tabelle ist der Linkername für verschiedene Aufrufkonventionen dargestellt.

|Aufrufkonvention|extern "C" oder c-Datei|.cpp, .cxx oder/TP|
|------------------------|---------------------------|------------------------|
|C-Namenskonvention (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Fastcall-Benennungskonvention (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|Standardmäßige Aufrufbenennungskonvention (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vectorcall-Namenskonvention (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

Verwenden Sie cxtern "C", um eine C-Funktion von C++ aus aufzurufen. Extern "C" erzwingt die C-Benennungskonvention für nicht klassenbasierte C++-Funktionen. Achten Sie besonders vorsichtig bei Compilerschaltern **/TC** oder **/TP**, die den Compiler anweisen, die Dateierweiterung zu ignorieren und die Datei als C oder C++ kompiliert. Diese Optionen führen möglicherweise zu unerwarteten Namen.

Funktionsprototypen mit nicht übereinstimmenden Parametern können auch zu diesem Fehler führen. Namensergänzungen fügen die Parameter einer Funktion in den endgültigen ergänzten Funktionsnamen ein. Durch Aufrufen einer Funktion mit den Parametertypen, die nicht mit denen in der Funktionsdeklaration übereinstimmen, kann ebenfalls LNK2001 verursacht werden.

Es gibt derzeit keinen Standard für die C++-Benennung zwischen Compileranbietern oder sogar zwischen unterschiedlichen Versionen eines Compilers. Durch Verknüpfen von Objektdateien, die mit anderen Compilern kompiliert wurden, wird daher möglicherweise nicht dasselbe Benennungsschema erstellt; dies führt daher zu nicht aufgelösten Externen.

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)