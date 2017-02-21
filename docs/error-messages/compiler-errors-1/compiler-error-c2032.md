---
title: "Compilerfehler C2032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2032"
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Die Funktion kann kein Member von Struktur\/Union 'StrukturOderUnion' sein  
  
 Die Struktur oder Union verfügt über eine Memberfunktion, die zwar in C\+\+, nicht aber in C zulässig ist.  Um den Fehler zu beheben, kompilieren Sie die Daten als C\+\+\-Programm oder entfernen die Memberfunktion.  
  
 Im folgenden Beispiel wird C2032 generiert:  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```