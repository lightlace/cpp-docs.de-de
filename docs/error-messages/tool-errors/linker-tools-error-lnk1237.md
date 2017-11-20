---
title: Linkertoolfehler Lnk1237 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1237
dev_langs: C++
helpviewer_keywords: LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43ab77f153b6e53709422a1826a6beee25d65b2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1237"></a>Linkertoolfehler LNK1237
Bei der codegenerierung eingeführt Compiler Verweis auf das Symbol 'Symbol' im Modul "Module", die mit/GL kompilierten definiert  
  
 Während der codegenerierung von, sollte der Compiler keine Symbole, die später in Definitionen, die kompiliert aufgelöst werden einführen **/GL**. `symbol`ist ein Symbol, das aufgelöst wird, um eine Definition mit kompiliert **/GL**.  
  
 Weitere Informationen finden Sie unter [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).  
  
 Um LNK1237 zu beheben, kompilieren Sie das Symbol mit **/GL** oder [/Include (Symbolverweise erzwingen)](../../build/reference/include-force-symbol-references.md) um einen Verweis auf das Symbol zu erzwingen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK1237 generiert. Zum Beheben dieses Fehlers nicht initialisieren Sie das Array in LNK1237_a.cpp, und fügen **/ include: __chkstk** auf den Linkbefehl.  
  
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