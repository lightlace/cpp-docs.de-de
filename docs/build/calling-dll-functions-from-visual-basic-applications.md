---
title: Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen | Microsoft Docs
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
ms.openlocfilehash: 9877544635dc894bbe379c751de35297add91c9d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367081"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus
Damit Visual Basic-Anwendungen (oder Anwendungen in anderen Sprachen wie Pascal oder Fortran) Funktionen in einer C-/C++-DLL aufrufen können, müssen die Funktionen mit der richtigen Aufrufkonvention exportiert werden, ohne dass der Compiler Namensergänzungen vornimmt.  
  
 Mithilfe von `__stdcall` wird zwar die richtige Aufrufkonvention für die Funktion erstellt (die aufgerufene Funktion bereinigt den Stapel, und die Parameter werden von rechts nach links übergeben), der Funktionsname wird jedoch unterschiedlich ergänzt. Daher werden beim **__declspec(dllexport)** wird verwendet, auf eine exportierte Funktion in einer DLL, wird der ergänzte Name exportiert.  
  
 Durch die `__stdcall`-Namensergänzung beginnt der Symbolname mit einem Unterstrich (_) und endet mit einem @-Zeichen, gefolgt von der Anzahl Bytes in der Argumentliste (dem erforderlichen Stapelplatz). Ist daher eine Funktion wie folgt deklariert:  
  
```  
int __stdcall func (int a, double b)  
```  
  
 wird sie folgendermaßen ergänzt:  
  
```  
_func@12  
```  
  
 Durch die C-Aufrufkonvention (`__cdecl`) wird der Name mit `_func` ergänzt.  
  
 Verwenden Sie zum Abrufen des ergänzten Namens [/MAP](../build/reference/map-generate-mapfile.md). Verwenden von **__declspec(dllexport)** bewirkt Folgendes:  
  
-   Wenn die Funktion mit C-Aufrufkonvention exportiert werden (**_cdecl**), den führenden Unterstrich (_) entfernt, wenn der Name exportiert wird.  
  
-   Wenn für die exportierte Funktion nicht die C-Aufrufkonvention (z. B. `__stdcall`) verwendet wird, wird der ergänzte Name exportiert.  
  
 Da es keine Möglichkeit gibt, die Stapelbereinigung an einer bestimmten Stelle zu überschreiben, muss `__stdcall` verwendet werden. Um eine Namensergänzung mit `__stdcall` rückgängig zu machen, müssen Sie sie im EXPORTS-Abschnitt der DEF-Datei mittels Aliasen angeben. Dies wird anhand der folgenden Funktionsdeklaration veranschaulicht:  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 In der DEF-Datei:  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Damit DLLs durch Programme in Visual Basic aufgerufen werden können, wird die in diesem Artikel erwähnte Aliastechnik in der DEF-Datei benötigt. Wenn das Aliasing im Visual Basic-Programm durchgeführt wird, ist es in der DEF-Datei nicht notwendig. In Visual Basic-Programm eine Aliasklausel hinzufügen durchgeführt werden die [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) Anweisung.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)  
  
-   [Exportieren aus einer DLL verwenden. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Bestimmen der geeigneten Exportmethode verwendet](../build/determining-which-exporting-method-to-use.md)  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)