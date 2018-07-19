---
title: Compilerfehler Fehler C2061 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4d4b018dbab16e8e376a3331a85d0f1b1004f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167378"
---
# <a name="compiler-error-c2061"></a>Compilerfehler Fehler C2061
Syntaxfehler: Bezeichner "Identifier"  
  
 Der Compiler hat einen Bezeichner, obwohl er erwartet wurde nicht gefunden. Stellen Sie sicher, dass `identifier` deklariert wird, bevor Sie ihn verwenden.  
  
 Ein Initialisierer möglicherweise in Klammern eingeschlossen sein. Um dieses Problem zu vermeiden, schließen Sie den Deklarator in Klammern ein, oder stellen sie eine `typedef`.  
  
 Dieser Fehler kann auch verursacht werden, wenn der Compiler einen Ausdruck als Klassenvorlagenargument erkennt; Verwenden Sie [Typename](../../cpp/typename.md) um den Compiler aufzufordern, dieser Typ ist ein.  
  
 Im folgenden Beispiel wird C2061 generiert:  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 kann auftreten, wenn Sie einen Instanznamen an übergeben [Typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```