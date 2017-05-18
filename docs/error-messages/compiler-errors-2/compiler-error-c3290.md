---
title: Compilerfehler C3290 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3290
dev_langs:
- C++
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 70cb6104f0aca5ae0e33cad2042d34a52cdc1945
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3290"></a>Compilerfehler C3290
"Typ": Eine trivial-Eigenschaft darf keinen Referenztyp aufweisen.  
  
 Eine Eigenschaft wurde falsch deklariert. Wenn Sie eine triviale Eigenschaft deklarieren, erstellt der Compiler eine Variable, die von der Eigenschaft aktualisiert wird, und es ist nicht möglich, eine Nachverfolgungsverweisvariable in einer Klasse zu verwenden.  
  
 Finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [Verweisoperator nachverfolgen](../../windows/tracking-reference-operator-cpp-component-extensions.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3290 generiert.  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```
