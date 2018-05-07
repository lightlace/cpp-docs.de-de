---
title: Compilerfehler C3268 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3268
dev_langs:
- C++
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ddc36fcfdc62983a90e39e04433052a256633a13
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3268"></a>Compilerfehler C3268
„function“: Eine generische Funktion oder eine Memberfunktion einer generischen Klasse darf keine Variablenparameterliste haben.  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3268 generiert:  
  
```  
// C3268.cpp  
// compile with: /clr:pure /c  
generic <class ItemType>  
void Test(ItemType item, ...) {}   // C3268  
// try the following line instead  
// void Test(ItemType item) {}  
  
generic <class ItemType2>  
ref struct MyStruct { void Test(...){} };   // C3268  
// try the following line instead  
// ref struct MyStruct { void Test2(){} };   // OK  
```