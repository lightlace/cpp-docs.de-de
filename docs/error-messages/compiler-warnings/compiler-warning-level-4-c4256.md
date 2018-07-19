---
title: Compilerwarnung (Stufe 4) C4256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4256
dev_langs:
- C++
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed1a40f0da75460c4306f69da0f26eb0888bef66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297221"
---
# <a name="compiler-warning-level-4-c4256"></a>Compilerwarnung (Stufe 4) C4256
'Funktion': Konstruktor für die Klasse mit virtuellen Basen besitzt "..."; Aufrufe möglicherweise nicht kompatibel mit früheren Versionen von Visual C++  
  
 Mögliche Inkompatibilität.  
  
 Betrachten Sie folgendes Codebeispiel. Wenn die Definition des Konstruktors S2::S2 (Int i,...) wurde mit einer Version von Visual C++-Compiler vor Version 7, kompiliert, aber im folgende Beispiel wird mit der aktuellen Version kompiliert, funktioniert der Aufruf des Konstruktors für S3 nicht ordnungsgemäß aufgrund der eine Änderung des Sonderfällen-Aufrufkonvention. Wenn beide mit Visual C++ 6.0 kompiliert wurden, würde der Aufruf nicht ganz rechts, funktionieren nur, wenn keine Parameter für die Auslassungszeichen übergeben wurden.  
  
 Um diese Warnung zu beheben,  
  
1.  Verwenden Sie keine Auslassungszeichen in einem Konstruktor.  
  
2.  Stellen Sie sicher, dass alle Komponenten in ihrem Projekt, mit der aktuellen Version erstellt werden (einschließlich der Bibliotheken, die definieren, oder verweisen auf diese Klasse können), und deaktivieren Sie die Warnung mit der [Warnung](../../preprocessor/warning.md) Pragma.  
  
 Im folgenden Beispiel wird C4256 generiert:  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```