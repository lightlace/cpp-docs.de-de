---
title: Nullptr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nullptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1bcfee3f408f6815e51740f9fc02d842afaa4d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419642"
---
# <a name="nullptr"></a>nullptr
Legt eine NULL-Zeiger-Konstante vom Typ `std::nullptr_t` fest, der in einen beliebigen unformatierten Zeigertyp konvertiert werden kann.  Sie können das Schlüsselwort `nullptr` zwar ohne Header verwenden, doch wenn der Code den Typ `std::nullptr_t` verwendet, müssen Sie es definieren, indem Sie den Header `<cstddef>` einschließen.  
  
> [!NOTE]
>  Das Schlüsselwort `nullptr` wird in C++/CLI auch für verwaltete Codeanwendungen definiert und ist nicht mit dem C++-ISO-Standard-Schlüsselwort austauschbar. Wenn mithilfe der Code kompiliert werden möglicherweise die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption), die verwalteten Code ausgerichtet ist, verwenden Sie dann `__nullptr` in einer beliebigen Codezeile, in denen Sie sicherstellen müssen, dass der Compiler die systemeigene C++-Interpretation verwendet. Weitere Informationen finden Sie unter [Nullptr](../windows/nullptr-cpp-component-extensions.md).  
  
## <a name="remarks"></a>Hinweise  
 Vermeiden Sie `NULL` oder 0 (`0`) als NULL-Zeiger-Konstante. `nullptr` ist weniger gefährdet, missbräuchlich verwendet zu werden, und funktioniert in den meisten Situationen besser.  Beispiel: Wenn `func(std::pair<const char *, double>)` vorgegeben ist, verursacht der Aufruf von `func(std::make_pair(NULL, 3.14))` einen Compilerfehler.  Die Makro-NULL wird auf `0` erweitert, sodass der Aufruf `std::make_pair(0, 3.14)` den Wert `std::pair<int, double>` zurückgibt, der nicht in den Parametertyp `std::pair<const char *, double>` von func() konvertierbar ist.  Durch Aufrufen von `func(std::make_pair(nullptr, 3.14))` ist die Kompilierung erfolgreich, da `std::make_pair(nullptr, 3.14)` den Wert `std::pair<std::nullptr_t, double>` zurückgibt, der in `std::pair<const char *, double>` konvertiert werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)