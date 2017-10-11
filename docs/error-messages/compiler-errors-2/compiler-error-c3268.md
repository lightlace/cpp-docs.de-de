---
title: Compilerfehler C3268 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3268
dev_langs:
- C++
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bab3adb4d6fd916eedaec36d455252b6a5ade454
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
