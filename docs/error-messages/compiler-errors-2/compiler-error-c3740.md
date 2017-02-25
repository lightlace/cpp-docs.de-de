---
title: "Compilerfehler C3740 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3740"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3740"
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3740
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorlagen können sich nicht auf Ereignisse beziehen oder sie erhalten  
  
 Eine von einer Vorlage gebildete Klasse oder Struktur kann keine [Ereignisse](../../cpp/event-handling.md) enthalten.  
  
 Im folgenden Beispiel wird C3740 generiert:  
  
```  
// C3740.cpp  
template <typename T>   // Delete the template specification  
struct E {  
   __event void f();   // C3740  
};  
  
int main() {  
}  
```