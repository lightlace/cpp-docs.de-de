---
title: Compilerfehler C2179 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2179
dev_langs:
- C++
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c12d7235cc146f080d74ffb09361dd691f7e1ba9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2179"></a>Compilerfehler C2179
'Typ': Ein Attributargument kann keine Typparameter verwenden  
  
 Ein generischer Typparameter ist zur Laufzeit aufgelöst. Ein Attributparameter muss jedoch zum Zeitpunkt der Kompilierung aufgelöst werden. Deshalb ist es nicht möglich, einen generischen Typparameter als Argument für ein Attribut verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2179 generiert.  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```