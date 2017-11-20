---
title: __super | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __super_cpp
dev_langs: C++
helpviewer_keywords: __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6dd4e24b36811a96e0d09ae58e7573d57065e2fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="super"></a>__super
**Microsoft-spezifisch**  
  
 Ermöglicht es Ihnen, explizit anzugeben, dass Sie eine Basisklassenimplementierung für eine Funktion aufrufen, die Sie überschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle verfügbaren Basisklassenmethoden werden während der Überladungsauflösungsphase berücksichtigt, und die Funktion, die die beste Übereinstimmung bereitstellt, ist die, die aufgerufen wird.  
  
 `__super` kann nur innerhalb des Texts einer Memberfunktion stehen.  
  
 `__super` kann nicht mit einer using-Deklaration verwendet werden. Finden Sie unter [using-Deklaration](../cpp/using-declaration.md) für Weitere Informationen.  
  
 Durch die Einführung des [Attribute](../windows/cpp-attributes-reference.md) , die Code einfügen, kann der Code enthält möglicherweise eine oder mehrere Basisklassen, deren Namen Sie möglicherweise nicht, die aber kennen enthalten Methoden, die Sie aufrufen möchten.  
  
## <a name="example"></a>Beispiel  
  
```  
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