---
title: Compilerfehler C3722 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3722
dev_langs:
- C++
helpviewer_keywords:
- C3722
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c12b977fa0f0ac31eb6ba472e738bd5692725f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3722"></a>Compilerfehler C3722
ein allgemeines Ereignis ist nicht zulässig.  
  
 Der Compiler lässt nur generische Klassen, Strukturen und Funktionen.  Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3722 generiert:  
  
```  
// C3722.cpp  
// compile with: /clr  
generic <typename T>  
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);  
  
generic <class T>  
public ref struct MyButton {  
   generic<typename U>  
   event MyEventHandler<U>^ Click;   // C3722  
};  
```