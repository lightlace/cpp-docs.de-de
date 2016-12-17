---
title: "nullptr"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "nullptr_cpp"
  - "nullptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nullptr-Schlüsselwort [C++]"
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt eine NULL\-Zeiger\-Konstante vom Typ `std::nullptr_t` fest, der in einen beliebigen unformatierten Zeigertyp konvertiert werden kann.  Sie können das Schlüsselwort `nullptr` zwar ohne Header verwenden, doch wenn der Code den Typ `std::nullptr_t` verwendet, müssen Sie es definieren, indem Sie den Header `<cstddef>` einschließen.  
  
> [!NOTE]
>  Das Schlüsselwort `nullptr` wird in C\+\+\/CLI auch für verwaltete Codeanwendungen definiert und ist nicht mit dem C\+\+\-ISO\-Standard\-Schlüsselwort austauschbar.  Wenn der Code möglicherweise mit der Compileroption [\/clr](../build/reference/clr-common-language-runtime-compilation.md) kompiliert wird, die auf verwalteten Code ausgerichtet ist, verwenden Sie `__nullptr` in einer Codezeile, in der Sie sicherstellen müssen, dass der Compiler die systemeigene C\+\+\-Interpretation verwendet.  Weitere Informationen finden Sie unter [nullptr](../windows/nullptr-cpp-component-extensions.md).  
  
## Hinweise  
 Vermeiden Sie `NULL` oder 0 \(`0`\) als NULL\-Zeiger\-Konstante. `nullptr` ist weniger gefährdet, missbräuchlich verwendet zu werden, und funktioniert in den meisten Situationen besser.  Beispiel: Wenn `func(std::pair<const char *, double>)` vorgegeben ist, verursacht der Aufruf von `func(std::make_pair(NULL, 3.14))` einen Compilerfehler.  Die Makro\-NULL wird auf `0` erweitert, sodass der Aufruf `std::make_pair(0, 3.14)` den Wert `std::pair<int, double>` zurückgibt, der nicht in den Parametertyp `std::pair<const char *, double>` von func\(\) konvertierbar ist.  Durch Aufrufen von `func(std::make_pair(nullptr, 3.14))` ist die Kompilierung erfolgreich, da `std::make_pair(nullptr, 3.14)` den Wert `std::pair<std::nullptr_t, double>` zurückgibt, der in `std::pair<const char *, double>` konvertiert werden kann.  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)