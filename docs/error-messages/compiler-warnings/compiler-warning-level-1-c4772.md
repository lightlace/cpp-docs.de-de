---
title: "Compilerwarnung (Stufe 1) C4772"
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
  - "C4772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4772"
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit \#import wurde auf einen Typ aus einer fehlenden Typbibliothek verwiesen; 'fehlender\_Typ' als Platzhalter verwendet  
  
 Auf eine Typbibliothek wurde mit der [\#import](../../preprocessor/hash-import-directive-cpp.md)\-Direktive verwiesen.  Die Typbibliothek enthielt jedoch einen Verweis auf eine andere Typbibliothek, auf die nicht mit `#import` verwiesen wurde.  Diese andere TLB\-Datei wurde vom Compiler nicht gefunden.  
  
 Beachten Sie, dass der Compiler keine Typbibliotheken in unterschiedlichen Verzeichnissen findet, wenn Sie die Compileroption [\/I \(Zusätzliche Includeverzeichnisse\)](../../build/reference/i-additional-include-directories.md) für die Angabe dieser Verzeichnisse verwenden.  Damit der Compiler Typbibliotheken in unterschiedlichen Verzeichnissen findet, fügen Sie diese in der Umgebungsvariablen PATH hinzu.  
  
 Diese Warnung wird standardmäßig als Fehler ausgegeben.  C4772 kann nicht mit **\/W0** unterdrückt werden.  
  
## Beispiel  
 Dies ist die erste Typbibliothek, die zum Reproduzieren von C4772 benötigt wird.  
  
```  
// c4772a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C4772aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]  
   enum E_C4772a  
   {  
      one, two, three  
   };  
};  
```  
  
## Beispiel  
 Dies ist die zweite Typbibliothek, die zum Reproduzieren von C4772 benötigt wird.  
  
```  
// c4772b.idl  
// post-build command: del /f C4772a.tlb  
// C4772a.tlb is available when c4772b.tlb is built  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4772bLib  
{  
   importlib ("c4772a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4772b  
   {  
      enum E_C4772a e;  
   };  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4772 generiert:  
  
```  
// C4772.cpp  
// assumes that C4772a.tlb is not available to the compiler  
// #import "C4772a.tlb"  
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve  
                       // and make sure c4772a.tlb is on disk  
```