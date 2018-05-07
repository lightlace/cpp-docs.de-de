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
ms.openlocfilehash: f184f0459e7ec2251d6ff34e2ee76559fe0dea42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3533"></a>Compilerfehler C3533
'Typ': ein Parameter keinen Typ, der "auto" enthält  
  
 Parameter-Methode oder die Vorlage kann nicht deklariert werden, mit der `auto` Schlüsselwort Wenn standardmäßig [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) (Compileroption) gültig ist.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `auto` -Schlüsselwort aus der Parameterdeklaration.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da es sich um einen Funktionsparameter mit deklariert die `auto` -Schlüsselwort, und es wird mit kompiliert **/Zc: Auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da sie mit einen Template-Parameter deklariert die `auto` -Schlüsselwort, und es wird mit kompiliert **/Zc: Auto**.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)   
 [/Zc:auto (Variablentyp ableiten)](../../build/reference/zc-auto-deduce-variable-type.md)