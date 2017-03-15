---
title: Compiler-Fehler C2429 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 7d2c27ccdba28720596984c46c9d24f9d29c7b15
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2429"></a>Compiler-Fehler C2429
'*Sprachfunktion*"erfordert das Compiler-Flag"*Compileroption*'  
  
Die Language-Funktion erfordert eine bestimmte Compileroption für Support.  
  
Der Fehler C2429: Sprachfunktion 'geschachtelt-Namespace-Definition' Compilerflag erfordert jedoch ' / Std:c ++ neueste "wird generiert, wenn Sie versuchen, definieren ein *zusammengesetzten Namespace*, einen Namespace, eine oder mehrere Bereich geschachtelt Namespacenamen, starten Visual Studio 2015 Update 3 enthält. Zusammengesetzte Namespace Definitionen in C++ vor C ++&17; sind unzulässig. Der Compiler unterstützt die zusammengesetzte Namespacedefinitionen bei der [/std:c ++ neueste](../../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben wird:  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
