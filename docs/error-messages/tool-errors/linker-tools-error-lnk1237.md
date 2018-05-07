---
title: Linkertoolfehler Lnk1237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ffc337d6b1548db4717dc4b87ff8aa25ef92e93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1237"></a>Linkertoolfehler LNK1237
Bei der codegenerierung eingeführt Compiler Verweis auf das Symbol 'Symbol' im Modul "Module", die mit/GL kompilierten definiert  
  
 Während der codegenerierung von, sollte der Compiler keine Symbole, die später in Definitionen, die kompiliert aufgelöst werden einführen **/GL**. `symbol` ist ein Symbol, das aufgelöst wird, um eine Definition mit kompiliert **/GL**.  
  
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