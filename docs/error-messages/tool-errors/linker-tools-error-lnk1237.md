---
title: "Linkertoolfehler LNK1237"
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
  - "LNK1237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1237"
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Während der Codegenerierung wurde in dem mit \/GL kompilierten Modul 'Modul' vom Compiler ein Verweis auf das Symbol 'Symbol' eingeführt.  
  
 Während der Codegenerierung sollten vom Compiler keine Symbole eingeführt werden, die zu einem späteren Zeitpunkt in Definitionen aufgelöst werden, die mit **\/GL** kompiliert werden.  Bei `symbol` handelt es sich um ein Symbol, das in eine Definition aufgelöst wird, die mit **\/GL** kompiliert wird.  
  
 Weitere Informationen finden Sie unter [\/GL \(Optimierung des ganzen Programms\)](../../build/reference/gl-whole-program-optimization.md).  
  
 Um LNK1237 zu vermeiden, kompilieren Sie das Symbol nicht mit **\/GL**, und erzwingen Sie keinen Verweis auf das Symbol mithilfe von [\/INCLUDE \(Symbolverweise erzwingen\)](../../build/reference/include-force-symbol-references.md).  
  
## Beispiel  
 Im folgenden Beispiel wird LNK1237 generiert.  Um diesen Fehler zu beheben, initialisieren Sie das Array nicht in LNK1237\_a.cpp, und fügen Sie dem Linkbefehl **\/include:\_\_chkstk** hinzu.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```