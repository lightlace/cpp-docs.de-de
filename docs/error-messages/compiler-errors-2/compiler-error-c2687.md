---
title: "Compilerfehler C2687 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2687"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2687"
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2687
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**"**   
 ***Typ* ": exception\-Deklaration darf nicht "void" sein oder einen unvollständigen Typ, Zeiger oder Verweis auf einen unvollständigen Typ kennzeichnen.**  
  
 Damit ein Typ einer Ausnahmedeklaration angehören kann, muss er definiert sein und darf nicht den Typ `void` haben.  
  
 Im folgenden Beispiel wird C2687 generiert:  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```