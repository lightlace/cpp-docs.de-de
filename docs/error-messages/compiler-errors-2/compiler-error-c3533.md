---
title: Compilerfehler C3533 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7bcd9c710ac5cdd50b966a72291918459d984be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 [/ Zc: Auto (Variablentyp ableiten)](../../build/reference/zc-auto-deduce-variable-type.md)