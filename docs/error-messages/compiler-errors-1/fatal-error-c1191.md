---
title: "Schwerwiegender Fehler C1191"
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
  - "C1191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1191"
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'dll' kann nur für globalen Gültigkeitsbereich importiert werden  
  
 Die Anweisung, mscorlib.dll in ein Programm zu importieren, das \/clr\-Programmierung verwendet, kann nicht in einem Namespace oder einer Funktion verwendet werden, sondern muss im globalen Gültigkeitsbereich enthalten sein.  
  
 Im folgenden Beispiel wird C1191 generiert:  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```