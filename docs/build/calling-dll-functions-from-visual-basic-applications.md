---
title: Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47504b7a471dc38f30e4ceb59b5feeffcc53db6d
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161832"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus

Für Visual Basic-Anwendungen (oder Anwendungen in anderen Sprachen wie Pascal oder Fortran) Funktionen in einer C/C++-DLL aufrufen müssen die Funktionen exportiert werden bei Verwendung der richtigen Aufrufkonvention ohne vom Compiler namensergänzungen

Mithilfe von `__stdcall` wird zwar die richtige Aufrufkonvention für die Funktion erstellt (die aufgerufene Funktion bereinigt den Stapel, und die Parameter werden von rechts nach links übergeben), der Funktionsname wird jedoch unterschiedlich ergänzt. Daher werden beim **__declspec(dllexport)** wird verwendet, auf eine exportierte Funktion in einer DLL, wird der ergänzte Name exportiert.

Die `__stdcall` namensergänzung beginnt der Symbolname mit einem Unterstrich ( **\_** ) und endet mit einem at-Zeichen (**\@**) Zeichens, gefolgt von der Anzahl von Bytes in der Argumentliste (dem erforderlichen Stapelplatz). Ist daher eine Funktion wie folgt deklariert:

```C
int __stdcall func (int a, double b)
```

wird als ergänzt `_func@12` in der Ausgabe.

Durch die C-Aufrufkonvention (`__cdecl`) wird der Name mit `_func` ergänzt.

Verwenden Sie zum Abrufen des ergänzten Namens [/MAP](../build/reference/map-generate-mapfile.md). Verwenden von **__declspec(dllexport)** bewirkt Folgendes:

- Wenn die Funktion der C-Aufrufkonvention exportiert wird (`__cdecl`), entfernt den führenden Unterstrich ( **\_** ) Wenn der Name wird exportiert.

- Wenn für die exportierte Funktion nicht die C-Aufrufkonvention (z. B. `__stdcall`) verwendet wird, wird der ergänzte Name exportiert.

Da es keine Möglichkeit gibt, die Stapelbereinigung an einer bestimmten Stelle zu überschreiben, muss `__stdcall` verwendet werden. Um eine Namensergänzung mit `__stdcall` rückgängig zu machen, müssen Sie sie im EXPORTS-Abschnitt der DEF-Datei mittels Aliasen angeben. Dies wird anhand der folgenden Funktionsdeklaration veranschaulicht:

```C
int  __stdcall MyFunc (int a, double b);
void __stdcall InitCode (void);
```

In der DEF-Datei:

```
EXPORTS
   MYFUNC=_MyFunc@12
   INITCODE=_InitCode@0
```

Damit DLLs durch Programme in Visual Basic aufgerufen werden können, wird die in diesem Artikel erwähnte Aliastechnik in der DEF-Datei benötigt. Wenn das Aliasing im Visual Basic-Programm durchgeführt wird, ist es in der DEF-Datei nicht notwendig. Es kann hierzu in Visual Basic-Programm eine Aliasklausel Hinzufügen der [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) Anweisung.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)

- [Exportieren aus einer DLL. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)

- [Exportieren aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Bestimmen der geeigneten Exportmethode verwendet](../build/determining-which-exporting-method-to-use.md)

- [Ergänzte Namen](../build/reference/decorated-names.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)
