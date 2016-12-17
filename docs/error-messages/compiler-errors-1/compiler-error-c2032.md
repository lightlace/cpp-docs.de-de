---
title: "Compilerfehler C2032"
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
  - "C2032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2032"
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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