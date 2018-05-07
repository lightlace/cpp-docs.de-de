---
title: Linkertoolfehler Lnk1313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1313
dev_langs:
- C++
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613c2069443e580fb581798d9e1cc6d5781d7c91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1313"></a>Linkertoolfehler LNK1313
IJW/Native-Modul gefunden; kann mit reinen Modulen nicht verknüpft werden  
  
 Die aktuelle Version von Visual C++ unterstützt nicht das Verknüpfen von systemeigenen oder gemischten verwalteten/systemeigenen .obj-Dateien mit OBJ-Dateien kompiliert mit **/CLR: pure**.  
  
## <a name="example"></a>Beispiel  
  
```  
// LNK1313.cpp  
// compile with: /c /clr:pure  
// a pure module  
int main() {}  
```  
  
## <a name="example"></a>Beispiel  
  
```  
// LNK1313_b.cpp  
// compile with: /c /clr  
// an IJW module  
void test(){}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird LNK1313 generiert.  
  
```  
// LNK1313_c.cpp  
// compile with: /link LNK1313.obj LNK1313_b.obj  
// LNK1313 warning expected  
```