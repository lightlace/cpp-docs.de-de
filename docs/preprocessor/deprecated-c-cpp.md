---
title: veraltet (C/C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
dev_langs:
- C++
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5df80fffb5b9cdeabfe19d5a5de6eb771d35d3d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="deprecated-cc"></a>deprecated (C/C++)
Die **veraltet** Pragma ermöglicht es Ihnen anzugeben, dass eine Funktion, Typ oder ein anderer Bezeichner in der Zukunft nicht mehr unterstützt werden möglicherweise freigegeben oder nicht mehr verwendet werden soll.  
> [!NOTE]
> Informationen zu den C ++ 14 `[[deprecated]]` Attribut und Hinweise dazu, wann verwendet Vs Attribut, das Microsoft-Declspec oder Pragma, finden Sie unter [Standard C++-Attribute](../cpp/attributes2.md) Attribut.
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Compiler erkennt einen Bezeichner, der gemäß einem **veraltet** Pragma ausgestellten compilerwarnung [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).   
  
 Sie können Makronamen als veraltet deklarieren. Platzieren Sie den Makronamen in Anführungszeichen; andernfalls tritt eine Makroerweiterung auf.  
  
 Da die **veraltet** Pragma kann für alle übereinstimmenden IDs und nimmt kein Signaturen berücksichtigt, es ist nicht die beste Option für bestimmte Versionen von überladenen Funktionen eingestellt. Alle übereinstimmenden Funktionsname, die eingebunden ist wird die Warnung ausgelöst.

  Es wird empfohlen, die C ++ 14 `[[deprecated]]` Attribut, nach Möglichkeit anstelle der **veraltet** Pragma. Der Microsoft-spezifische [__declspec(deprecated)](../cpp/deprecated-cpp.md) deklarationsmodifizierer ist die bessere Wahl in vielen Fällen als auch die **veraltet** Pragma. Die `[[deprecated]]` Attribut und `__declspec(deprecated)` Modifizierer ermöglichen es Ihnen, die für bestimmte Arten von überladenen Funktionen als veraltet markierte Status angeben. Die Diagnose Warnung wird nur angezeigt, für Verweise auf den bestimmten überladenen Funktion das Attribut oder Modifizierer betrifft.  
  
## <a name="example"></a>Beispiel  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 Das folgende Beispiel zeigt, wie Sie eine Klasse als veraltet deklarieren:  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)