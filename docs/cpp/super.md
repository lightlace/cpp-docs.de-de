---
title: __super | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9caa3d08140887da45916b931b6a4850358db16
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943967"
---
# <a name="super"></a>__super
**Microsoft-spezifisch**  
  
 Ermöglicht es Ihnen, explizit anzugeben, dass Sie eine Basisklassenimplementierung für eine Funktion aufrufen, die Sie überschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
__super::member_function();  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle verfügbaren Basisklassenmethoden werden während der Überladungsauflösungsphase berücksichtigt, und die Funktion, die die beste Übereinstimmung bereitstellt, ist die, die aufgerufen wird.  
  
 **__super** kann nur innerhalb des Texts einer Memberfunktion verwendet werden.  
  
 **__super** kann nicht verwendet werden, mithilfe einer Deklaration. Finden Sie unter [using-Deklaration](../cpp/using-declaration.md) für Weitere Informationen.  
  
 Mit der Einführung von [Attribute](../windows/cpp-attributes-reference.md) , die Code einfügen, kann Ihr Code enthält eine oder mehrere Basisklassen, deren Namen Sie möglicherweise nicht, die aber kennen Methoden enthalten, die Sie aufrufen möchten.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)