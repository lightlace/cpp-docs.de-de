---
title: "Compilerwarnung (Stufe 1) C4342 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4342"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4342"
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 1) C4342
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verhaltensänderung: 'Funktion' wird aufgerufen, in früheren Versionen wurde jedoch ein Memberoperator aufgerufen.  
  
 In früheren Versionen von Visual C\+\+ wurde ein Member aufgerufen. Dieses Verhalten wurde jedoch geändert, und der Compiler sucht im Gültigkeitsbereich des Namespaces nach dem Operator mit der besten Übereinstimmung.  
  
 Wenn ein Memberoperator gefunden wurde, wurden vom Compiler bislang Operatoren im Gültigkeitsbereich des Namespaces ignoriert.  Wenn vom aktuellen Compiler ein Operator mit besserer Übereinstimmung im Gültigkeitsbereich des Namespaces gefunden wird, wird dieser ordnungsgemäß aufgerufen. Frühere Versionen des Compilers zeigen dieses Verhalten nicht.  
  
 Diese Warnung sollte deaktiviert werden, nachdem Sie den Code erfolgreich in die aktuelle Version portiert haben.  Unter Umständen wird diese Warnung durch den Compiler fälschlicherweise für Code ausgegeben, für den keine Verhaltensänderung vorliegt.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4342 generiert:  
  
```  
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