---
title: Compilerwarnung (Stufe 1) C4342 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4342
dev_langs: C++
helpviewer_keywords: C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7d2a3550a3d1b7333412b7828809120db89c60b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4342"></a>Compilerwarnung (Stufe 1) C4342
verhaltensänderung: '*Funktion*"aufgerufen wird, jedoch ein Memberoperator aufgerufen wurde, in früheren Versionen  
  
 In Versionen von Visual C++ vor Visual Studio 2002 ein Element aufgerufen wurde, aber dieses Verhalten wurde geändert, und der Compiler findet die beste Übereinstimmung jetzt im Namespacebereich.  
  
 Wenn ein Memberoperator gefunden wurde, würde der Compiler zuvor keinen Namespaces Bereich Operatoren berücksichtigt. Ist eine bessere Übereinstimmung im Namespacebereich, ruft der aktuellen Compiler ordnungsgemäß, während der vorherige Compilern wäre nicht beachtet.  
  
 Diese Warnung sollte deaktiviert werden, nachdem erfolgreich Portieren von Code auf die aktuelle Version.  Der Compiler erzielen möglicherweise falsch positive Ergebnisse generiert diese Warnung für Code, keine verhaltensänderung erfolgt.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4342 generiert:  
  
```cpp  
// C4342.cpp  
// compile with: /EHsc /W1  
#include <fstream>  
#pragma warning(default: 4342)  
using namespace std;  
struct X : public ofstream {  
   X();  
};  
  
X::X() {  
   open( "ofs_bug_ev.txt." );  
   if ( is_open() ) {  
      *this << "Text" << "<-should be text" << endl;   // C4342  
      *this << ' ' << "<-should be space symbol" << endl;   // C4342  
   }  
}  
  
int main() {  
   X b;  
   b << "Text" << "<-should be text" << endl;  
   b << ' ' << "<-should be space symbol" << endl;  
}  
```