---
title: "Compilerwarnung (Stufe 1) C4311"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4311"
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Zeigerverkürzung von 'Typ' zu 'Typ'  
  
 Diese Warnung erkennt Abschneidefehler bei 64\-Bit\-Zeigern.  Wenn Code beispielsweise für eine 64\-Bit\-Architektur kompiliert wird, wird der Wert eines Zeigers \(64 Bit\) abgeschnitten, falls er einem `int` \(32 Bit\) zugewiesen wurde.  Weitere Informationen finden Sie unter [Regeln für die Verwendung von Zeigern](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 Weitere Informationen zu den häufigsten Gründen von Warnung C4311 finden Sie unter [Häufige Compilerfehler](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 Im folgenden Codebeispiel wird C4311 beim Kompilieren für ein 64\-Bit\-Ziel generiert und dann veranschaulicht, wie Sie dieses Problem beheben können:  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```