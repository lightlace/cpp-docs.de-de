---
title: "Aufrufen von DLL-Funktionen aus Visual&#160;Basic-Anwendungen heraus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__stdcall-Schlüsselwort [C++]"
  - "Aufrufen von DLL-Funktionen aus VB-Anwendungen [C++]"
  - "DLL-Funktionen [C++]"
  - "DLL-Funktionen [C++], Aufrufen"
  - "DLLs [C++], Aufrufen"
  - "Funktionsaufrufe [C++], DLL-Funktionen"
  - "Funktionen [C++], Aufrufen von DLL-Funktionen aus Visual Basic"
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Aufrufen von DLL-Funktionen aus Visual&#160;Basic-Anwendungen heraus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Damit Visual Basic\-Anwendungen \(oder Anwendungen in anderen Sprachen wie Pascal oder Fortran\) Funktionen in einer C\-\/C\+\+\-DLL aufrufen können, müssen die Funktionen mit der richtigen Aufrufkonvention exportiert werden, ohne dass der Compiler Namensergänzungen vornimmt.  
  
 Mithilfe von `__stdcall` wird zwar die richtige Aufrufkonvention für die Funktion erstellt \(die aufgerufene Funktion bereinigt den Stapel, und die Parameter werden von rechts nach links übergeben\), der Funktionsname wird jedoch unterschiedlich ergänzt.  Wird daher **\_\_declspec\(dllexport\)** für eine exportierte Funktion in einer DLL verwendet, wird der ergänzte Name exportiert.  
  
 Durch die `__stdcall`\-Namensergänzung beginnt der Symbolname mit einem Unterstrich \(\_\) und endet mit einem @\-Zeichen, gefolgt von der Anzahl Bytes in der Argumentliste \(dem erforderlichen Stapelplatz\).  Ist daher eine Funktion wie folgt deklariert:  
  
```  
int __stdcall func (int a, double b)  
```  
  
 wird sie folgendermaßen ergänzt:  
  
```  
_func@12  
```  
  
 Durch die C\-Aufrufkonvention \(`__cdecl`\) wird der Name mit `_func` ergänzt.  
  
 Um den ergänzten Namen zu ermitteln, verwenden Sie [\/MAP](../build/reference/map-generate-mapfile.md).  Die Verwendung von **\_\_declspec\(dllexport\)** bewirkt Folgendes:  
  
-   Wenn die Funktion nach der C\-Aufrufkonvention \(**\_cdecl**\) exportiert wird, wird beim Export der führende Unterstrich \(\_\) entfernt.  
  
-   Wenn für die exportierte Funktion nicht die C\-Aufrufkonvention \(z. B. `__stdcall`\) verwendet wird, wird der ergänzte Name exportiert.  
  
 Da es keine Möglichkeit gibt, die Stapelbereinigung an einer bestimmten Stelle zu überschreiben, muss `__stdcall` verwendet werden.  Um eine Namensergänzung mit `__stdcall` rückgängig zu machen, müssen Sie sie im EXPORTS\-Abschnitt der DEF\-Datei mittels Aliasen angeben.  Dies wird anhand der folgenden Funktionsdeklaration veranschaulicht:  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 In der DEF\-Datei:  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Damit DLLs durch Programme in Visual Basic aufgerufen werden können, wird die in diesem Artikel erwähnte Aliastechnik in der DEF\-Datei benötigt.  Wenn das Aliasing im Visual Basic\-Programm durchgeführt wird, ist es in der DEF\-Datei nicht notwendig.  Zu diesem Zweck wird der [Declare](../Topic/Declare%20Statement.md)\-Anweisung im Visual Basic\-Programm eine Aliasklausel hinzugefügt.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Bestimmen der geeigneten Exportmethode](../build/determining-which-exporting-method-to-use.md)  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)