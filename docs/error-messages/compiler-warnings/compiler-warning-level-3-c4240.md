---
title: "Compilerwarnung (Stufe 3) C4240 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4240"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4240"
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 3) C4240
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung verwendet : Zugriff auf 'Klassenname' ist jetzt als 'Zugriffsspezifizierer' definiert, wurde zuvor als 'Zugriffsspezifizierer' definiert  
  
 Bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) kann der Zugriff auf eine geschachtelte Klasse nicht geändert werden.  Bei Verwendung der Microsoft\-Standarderweiterungen \(**\/Ze**\) ist dies möglich, wobei jedoch diese Warnung ausgegeben wird.  
  
## Beispiel  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```