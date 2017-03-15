---
title: "Compilerfehler C3194 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3194"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3194"
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3194
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Ein Werttyp darf keinen Zuweisungsoperator aufweisen  
  
 Spezielle Memberfunktionen, die einen automatischen Aufruf durch den Compiler erfordern, z. B. ein Kopierkonstruktor oder ein Kopierzuweisungsoperator, werden innerhalb einer Wertklasse nicht unterstützt.  
  
## Beispiel  
 Im folgenden Beispiel wird C3194 generiert.  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```