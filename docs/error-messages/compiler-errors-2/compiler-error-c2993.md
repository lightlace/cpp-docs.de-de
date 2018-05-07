---
title: Compilerfehler C2993 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e25e70a9d16ee166772cf03ea1837afaf14cae29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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