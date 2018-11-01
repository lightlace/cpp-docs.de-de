---
title: dllexport, dllimport
ms.date: 11/04/2016
f1_keywords:
- dllimport_cpp
- dllexport_cpp
helpviewer_keywords:
- dllexport __declspec keyword
- __declspec keyword [C++], dllexport
- dllimport __declspec keyword
- __declspec keyword [C++], dllimport
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
ms.openlocfilehash: 2ae284172828ed63b6499475df108c28aecb32ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525956"
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport

**Microsoft-spezifisch**

Die **Dllexport** und **Dllimport** Speicherklassen-Attribute sind Microsoft-spezifische Erweiterungen der Programmiersprachen C und C++. Sie können sie verwenden, um Funktionen, Daten und Objekte in eine DLL zu exportieren oder von einer DLL zu importieren.

## <a name="syntax"></a>Syntax

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>Hinweise

Diese Attribute definieren explizit die Schnittstelle der DLL zu dem Client, der die ausführbare Datei oder eine andere DLL sein kann. Deklarieren von Funktionen als **Dllexport** überflüssig eine Moduldefinitionsdatei (.def)-Datei, zumindest in Bezug auf die Angabe von exportierten Funktionen. Die **Dllexport** -Attribut ersetzt das **__export** Schlüsselwort.

Wenn eine Klasse als "declspec(dllexport)" gekennzeichnet ist, werden alle Spezialisierungen von Klassenvorlagen in der Klassenhierarchie implizit als "declspec (dllexport)" gekennzeichnet. Das bedeutet, dass Klassenvorlagen explizit instanziiert werden und die Member der Klasse definiert werden müssen.

**Dllexport** einer Funktion macht die Funktion mit dem ergänzten Namen. Bei C++-Funktionen schließt dies Namenszerlegung mit ein. Bei C-Funktionen oder Funktionen, die als `extern "C"` deklariert werden, schließt dies plattfomspezifische Ergänzungen, die auf der Aufrufkonvention basieren, mit ein. Weitere Informationen zur namenserweiterung in C/C++-Code finden Sie unter [ergänzte Namen](../build/reference/decorated-names.md). Keine Namensergänzung gilt für exportierte C-Funktionen oder C++-`extern "C"`-Funktionen, die die `__cdecl`-Aufrufkonvention verwenden.

Um einen nicht ergänzten Namen zu exportieren, können Sie bei der Verknüpfung eine Moduldefinitionsdatei (.def) verwenden, die den nicht ergänzten Namen in einem EXPORTS-Abschnitt definiert. Weitere Informationen finden Sie unter [EXPORTE](../build/reference/exports.md). Eine weitere Möglichkeit zum Exportieren eines nicht ergänzten Namens ist die Verwendung einer `#pragma comment(linker, "/export:alias=decorated_name")` -Anweisung im Quellcode.

Wenn Sie deklarieren **Dllexport** oder **Dllimport**, verwenden Sie [erweiterte Attributsyntax](../cpp/declspec.md) und **__declspec** Schlüsselwort.

## <a name="example"></a>Beispiel

```cpp
// Example of the dllimport and dllexport class attributes
__declspec( dllimport ) int i;
__declspec( dllexport ) void func();
```

Um den Code lesbarer zu machen, können Sie alternativ Makrodefinitionen verwenden:

```cpp
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllImport int j;
DllExport int n;
```

Weitere Informationen finden Sie unter:

- [Definitionen und Deklarationen](../cpp/definitions-and-declarations-cpp.md)

- [Definieren von C++-Inlinefunktionen mit dllexport und dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [Allgemeine Regeln und Einschränkungen](../cpp/general-rules-and-limitations.md)

- [Verwenden von dllimport und dllexport in C++-Klassen](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)