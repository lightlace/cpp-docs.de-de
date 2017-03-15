---
title: "Compilerwarnung (Stufes 3 and 4) C4244 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Compilerwarnung (Stufes 3 and 4) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion': Umwandlung von 'type1' in 'type2', Datenverlust ist möglich  
  
 Ein ganzzahliger Typ wird in einen kleineren ganzzahligen Typ konvertiert.  Dies ist eine Warnung der Stufe 4, wenn *type1* gleich `int` und *type2* kleiner als `int` ist.  Andernfalls ist es eine Warnung der Stufe 3 \(ein Wert vom Typ [\_\_int64](../../cpp/int8-int16-int32-int64.md) wird einer Variablen vom Typ `unsigned int` zugewiesen\).  Möglicherweise ist ein Datenverlust aufgetreten.  
  
 Wenn C4244 angezeigt wird, sollten Sie das Programm für das Verwenden von kompatiblen Typen ändern Logik zu Ihrem Code hinzufügen, um sicherzustellen, dass der Bereich möglicher Werte immer mit den verwendeten Typen kompatibel sind.  
  
 C4244 kann auch auf Ebene 2 ausgelöst werden. Weitere Informationen finden Sie unter [Compilerwarnung \(Stufe 2\) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md).  
  
 Die Konvertierung hat möglicherweise ein Problem durch implizite Konvertierungen.  
  
 Im folgenden Beispiel wird C4244 generiert:  
  
```  
// C4244_level4.cpp  
// compile with: /W4  
int aa;  
unsigned short bb;  
int main() {  
   int b = 0, c = 0;  
   short a = b + c;   // C4244  
  
   bb += c;   // C4244  
   bb = bb + c;   // C4244  
   bb += (unsigned short)aa;   // C4244  
   bb = bb + (unsigned short)aa;   // OK  
}  
```  
  
 Weitere Informationen finden Sie unter [Übliche arithmetische Konvertierungen](../../c-language/usual-arithmetic-conversions.md).  
  
```  
// C4244_level3.cpp  
// compile with: /W3  
int main() {  
   __int64 i = 8;  
   unsigned int ii = i;   // C4244  
}  
```  
  
 Warnung C4244 kann auftreten, wenn Code für 64\-Bit\-Ziele erstellt wird, der keine Warnung generiert, wenn er für 32\-Bit\-Ziele erstellt wird.  Beispielsweise ist ein Unterschied zwischen Zeigern eine 32\-Bit\-Menge auf 32\-Bit\-Plattformen, aber eine 64\-Bit\-Menge auf 64\-Bit\-Plattformen.  
  
 Im folgenden Beispiel wird C4244 generiert, wenn für 64\-Bit\-Ziele kompiliert wird:  
  
```  
// C4244_level3_b.cpp  
// compile with: /W3   
int main() {  
   char* p1 = 0;  
   char* p2 = 0;  
   int x = p2 - p1;   // C4244  
}  
```