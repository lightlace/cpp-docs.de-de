---
title: "Compilerfehler C3154"
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
  - "C3154"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3154"
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3154
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

',' vor Auslassungszeichen erwartet.Nicht durch Trennzeichen getrennte Auslassungszeichen werden für Parameterarrayfunktionen nicht unterstützt.  
  
 Eine Funktion mit variablen Argumenten wurde nicht ordnungsgemäß deklariert.  
  
 Weitere Informationen finden Sie unter [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3154 generiert.  
  
```  
// C3154.cpp  
// compile with: /clr  
ref struct R {  
   void Func(int ... array<int> ^);   // C3154  
   void Func2(int i, ... array<int> ^){}   // OK  
   void Func3(array<int> ^){}   // OK  
   void Func4(... array<int> ^){}   // OK  
};  
  
int main() {  
   R ^ r = gcnew R;  
   r->Func4(1,2,3);  
}  
```