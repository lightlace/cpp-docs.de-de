---
title: "Compilerfehler C3894"
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
  - "C3894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3894"
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Die Verwendung des L\-Werts eines statischen initonly\-Datenmembers ist nur im Klassenkonstruktor der 'Klasse'\-Klasse zulässig.  
  
 Statische [initonly](../../dotnet/initonly-cpp-cli.md)\-Datenmember können nur als L\-Werte zum Zeitpunkt der Deklaration oder in einem statischen Konstruktor verwendet werden.  
  
 \(Nicht statische\) initonly\-Instanzendatenmember können nur als L\-Werte zum Zeitpunkt der Deklaration oder als \(nicht statische\) Instanzenkonstruktoren verwendet werden.  
  
 Im folgenden Beispiel wird C3894 generiert:  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```