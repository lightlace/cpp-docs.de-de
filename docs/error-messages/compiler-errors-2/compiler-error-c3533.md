---
title: Compilerfehler C3533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: faaf53d08512559b86c95148bc93e7b3367d2b01
ms.sourcegitcommit: 3bb7c1c0ceeb8012418e2fff9ae5a7db0fff3877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="compiler-error-c3533"></a>Compilerfehler C3533
'Typ': ein Parameter keinen Typ, der "auto" enthält  
  
 Parameter-Methode oder die Vorlage kann nicht deklariert werden, mit der `auto` Schlüsselwort Wenn standardmäßig [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) (Compileroption) gültig ist.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `auto` -Schlüsselwort aus der Parameterdeklaration.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ergibt C3533, da es sich um einen Funktionsparameter mit deklariert die `auto` -Schlüsselwort, und es wird mit kompiliert **/Zc: Auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j) {} // C3533  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ergibt C3533 in C ++ 14-Modus, da deklariert einen Vorlagenparameter, mit der `auto` -Schlüsselwort, und es wird mit kompiliert **/Zc: Auto**. (In C ++ 17 ist dies eine gültige Definition einer Klassenvorlage mit einem einzelnen Nichttyp-Vorlagenparameter, dessen Typ abgeleitet wird.)
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C {}; // C3533  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)   
 [/Zc:auto (Variablentyp ableiten)](../../build/reference/zc-auto-deduce-variable-type.md)
