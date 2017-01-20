---
title: "Compilerfehler C3874"
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
  - "C3874"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3874"
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3874
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Rückgabetyp von 'Funktion' sollte "int" anstatt 'Typ' sein  
  
 Eine Funktion hat bicht den vom Compiler erwarteten Rückgabetyp.  
  
 Im folgenden Beispiel wird C3874 generiert:  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```