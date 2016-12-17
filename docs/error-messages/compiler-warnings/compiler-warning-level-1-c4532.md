---
title: "Compilerwarnung (Stufe 1) C4532"
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
  - "C4532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4532"
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'continue': Aussprung aus \_\_finally\/finally\-Block weist ein undefiniertes Verhalten während der Abbruchbehandlung auf  
  
 Der Compiler hat eines der folgenden Schlüsselwörter gefunden:  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 Diese Schlüsselwörter verursachen bei einer vorzeitigen Beendigung einen Sprung aus einem [\_\_finally](../../cpp/try-finally-statement.md)\- oder [finally](../../dotnet/finally.md)\-Block.  
  
 Wenn eine Ausnahme auftritt, während der Stapel bei Ausführung des Beendigungshandlers \(des `__finally`\- oder finally\-Blockes\) entladen wird, und der Code vor Ende des `__finally`\-Blockes aus dem `__finally`\-Block herausspringt, ist das Verhalten nicht definiert.  Die Steuerung geht möglicherweise nicht an den entladenen Code zurück, sodass die Ausnahme u. U. nicht ordnungsgemäß verarbeitet wird.  
  
 Wenn Sie aus einem `__finally`\-Block herausspringen müssen, sollten Sie zuerst prüfen, ob eine vorzeitige Beendigung vorliegt.  
  
 Im folgenden Beispiel wird C4532 generiert. Um die Warnungen zu vermeiden, kommentieren Sie die Sprunganweisungen einfach aus.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```