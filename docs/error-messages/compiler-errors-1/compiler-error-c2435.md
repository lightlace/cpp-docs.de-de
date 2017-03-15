---
title: Compiler-Fehler C2435 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: dbc2045eae70cacd42e13ddb7cc8ecb3d60b8596
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2435"></a>Compilerfehler C2435
'Var': dynamische Initialisierung ist eine verwaltete CRT erforderlich ist, kann nicht mit/clr: safe kompiliert  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 veraltet sind.  
  
 Initialisierung einer globalen pro-AppDomain-Variablen erfordert eine kompilierte die CRT mit `/clr:pure`, die erzeugt kein überprüfbaren Abbilds.  
  
 Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md) und [Prozess](../../cpp/process.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2435 generiert:  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
