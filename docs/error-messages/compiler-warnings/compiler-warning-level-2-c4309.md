---
title: "Compilerwarnung (Stufe 2) C4309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4309"
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 2) C4309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konvertierung': Verkürzung eines konstanten Werts  
  
 Aufgrund der Typkonvertierung wurde der einer Konstanten zugeordnete Speicherplatz überschritten.  Möglicherweise müssen Sie einen größeren Typ für die Konstante verwenden.  
  
 Im folgenden Beispiel wird C4309 generiert:  
  
```  
// C4309.cpp  
// compile with: /W2  
int main()  
{  
   char c = 128;   // C4309  
}  
```