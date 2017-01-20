---
title: "Compilerwarnung (Stufe 4) C4571"
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
  - "C4571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4571"
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Information: Die catch\(...\)\-Semantik wurde gegenüber Visual C\+\+ 7.1 geändert; strukturierte Ausnahmen \(SEH\) werden nicht mehr abgefangen  
  
 C4571 wird bei Kompilierung mit **\/EHs** für jeden catch\(...\)\-Block generiert.  
  
 Beim Kompilieren mit **\/EHs** wird eine strukturierte Ausnahme \(z. B. Division durch 0 \(Null\), Nullzeiger\) nicht von einem catch\(...\)\-Block aufgefangen; catch\(...\)\-Blöcke fangen nur explizit ausgelöste C\+\+\-Ausnahmen auf.  Weitere Informationen finden Sie unter [Ausnahmebehandlung](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Diese Warnung ist standardmäßig deaktiviert.  Aktivieren Sie diese Warnung, um sicherzustellen, dass beim Kompilieren mit **\/EHs** die catch\(...\)\-Blöcke nicht zum Auffangen strukturierter Ausnahmen verwendet werden.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Zum Beheben des Fehlers C4571 bestehen folgende Möglichkeiten:  
  
-   Kompilieren Sie mit **\/EHa**, wenn catch\(...\)\-Blöcke weiterhin strukturierte Ausnahmen auffangen sollen.  
  
-   Aktivieren Sie C4571 nicht, wenn die catch\(...\)\-Blöcke keine strukturierten Ausnahmen auffangen sollen, Sie jedoch catch\(...\)\-Blöcke verwenden möchten.  Sie können strukturierte Ausnahmen auch weiterhin abfangen, indem Sie die Schlüsselwörter für strukturierte Ausnahmebehandlung verwenden \(**\_\_try**, **\_\_except** und **\_\_finally**\).  Beachten Sie jedoch, dass kompilierte **\/EHs**\-Destruktoren nur bei Auslösung von C\+\+\-Ausnahmen aufgerufen werden, nicht bei SEH\-Ausnahmen.  
  
-   Ersetzen Sie catch\(...\)\-Blöcke durch catch\-Blöcke für bestimmte C\+\+\-Ausnahmen, und fügen Sie der C\+\+\-Ausnahmebehandlung optional eine strukturierte Ausnahmebehandlung hinzu \(**\_\_try**, **\_\_except** und **\_\_finally**\).  Weitere Informationen finden Sie unter [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md).  
  
 Weitere Informationen finden Sie unter [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4571 generiert.  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```