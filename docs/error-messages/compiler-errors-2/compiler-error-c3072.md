---
title: "Compilerfehler C3072 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3072"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3072"
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3072
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Operator 'Operator' kann nicht auf eine Instanz einer Verweisklasse angewendet werden  
  
 Verwenden Sie den unären Operator '`operator`', um eine Instanz einer Verweisklasse in einen Handletyp zu konvertieren.  
  
 Ein CLR\-Typ erfordert Operatoren CLR, keine systemeigenen \(oder Standard\-\)Operatoren.  Weitere Informationen finden Sie unter [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3072 generiert.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```