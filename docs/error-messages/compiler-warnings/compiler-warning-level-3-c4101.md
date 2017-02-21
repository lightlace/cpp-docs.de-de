---
title: "Compilerwarnung (Stufe 3) C4101 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4101"
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 3) C4101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Unreferenzierte lokale Variable  
  
 Die lokale Variable wird keinesfalls verwendet.  Im folgenden Fall wird die Warnung eindeutig ausgegeben:  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 Die Warnung tritt jedoch auch auf, wenn eine **static**\-Memberfunktion durch eine Instanz der Klasse aufgerufen wird:  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 In dieser Situation greift der Compiler unter Verwendung der Informationen für `si` auf die **static**\-Funktion zu, die Klasseninstanz ist jedoch für den Aufruf der **static**\-Funktion nicht nötig, sodass wiederum die Warnung ausgegeben wird.  Sie haben folgende Möglichkeiten, um die Warnung aufzulösen:  
  
-   Fügen Sie einen Konstruktor hinzu, in dem der Compiler die Instanz von `si` für den Aufruf von `func` verwenden würde.  
  
-   Entfernen Sie das **static**\-Schlüsselwort aus der `func`\-Definition.  
  
-   Rufen Sie die **static**\-Funktion explizit auf: `int y = S::func();`.