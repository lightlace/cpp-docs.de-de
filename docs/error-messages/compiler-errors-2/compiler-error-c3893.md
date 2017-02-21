---
title: "Compilerfehler C3893 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3893"
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Die Verwendung des L\-Werts eines initonly\-Datenmembers ist nur in einem Instanzenkonstruktor der 'type\_name'\-Klasse zulässig  
  
 Statische [initonly](../../dotnet/initonly-cpp-cli.md)\-Datenmember können nur in einem statischen Konstruktor ihre Adresse übernehmen.  
  
 initonly\-Datenmember einer Instanz \(nicht statisch\) können nur in Instanzenkonstruktoren \(nicht statisch\) ihre Adresse übernehmen.  
  
 Im folgenden Beispiel wird C3893 generiert:  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```