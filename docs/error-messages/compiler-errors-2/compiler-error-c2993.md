---
title: Compilerfehler C2993 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6306b2c3c632d25ee6b37a025516f759cc126a6
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2993"></a>Compilerfehler C2993
'Bezeichner': Ungültiger Typ für den Nichttyp-Vorlagenparameter 'Parameter'  
  
 Sie können eine Vorlage mit einer Struktur oder union-Argument nicht deklarieren. Verwenden Sie Zeiger, um Strukturen und Unions als Vorlagenparameter übergeben.  
  
 Im folgende Beispiel wird C2993 generiert:  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Dieser Fehler wird außerdem infolge einer konformitätsverbesserung, die in Visual Studio .NET 2003 durchgeführt wurde generiert werden: Gleitkommawert Nichttyp-Vorlagenparameter nicht mehr erlaubt. Der C++-Standard lässt nicht Gleitkommazahlen Nichttyp-Vorlagenparameter.  
  
 Wenn es sich um eine Funktionsvorlage handelt, verwenden ein Funktionsargument in den Gleitkomma übergeben zeigen Nichttyp-Vorlagenparameter (in diesem Code wird in der Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig sein). Wenn sie eine Klassenvorlage ist, besteht keine einfache Lösung.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```
