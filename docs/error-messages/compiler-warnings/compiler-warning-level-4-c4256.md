---
title: "Compilerwarnung (Stufe 4) C4256 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4256"
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 4) C4256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Konstruktor für die Klasse mit virtuellen Basen besitzt '...'. Aufrufe sind möglicherweise nicht mit älteren Versionen von Visual C\+\+ kompatibel  
  
 Mögliche Inkompatibilität.  
  
 Betrachten Sie folgendes Codebeispiel.  Wenn die Definition des Konstruktors S2::S2 \(int i,... \) wurde kompiliert, wird eine Version des Visual C\+\+\-Compilers vor Version 7 verwendete, aber das folgende Beispiel wird, indem Sie die aktuelle Version, der Konstruktoraufruf für S3 verwendet, würde funktionieren ordnungsgemäß aufgrund einer Änderung kompiliert.  Wenn beide kompiliert wurden, indem Sie Visual C\+\+ 6.0 verwendete, würde der Aufruf nicht identisch mit rechten auch nicht bearbeiten, es sei denn, für das Auslassungszeichen wurden keine Parameter übergeben.  
  
 So vermeiden Sie diese Warnung:  
  
1.  Verwenden Sie keine Auslassungszeichen in einem Konstruktor.  
  
2.  Stellen Sie sicher, dass alle Komponenten im Projekt mit der aktuellen Version erstellt wurden \(einschließlich der Bibliotheken, durch die diese Klasse definiert oder referenziert wird\). Deaktivieren Sie die Warnung anschließend mit dem Pragma [warning](../../preprocessor/warning.md).  
  
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