---
title: Linkertoolwarnung Lnk4254 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e17bcd03f92114c1b7cd21e63220cf6372c17bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4254"></a>Linkertoolwarnung LNK4254
Abschnitt 'Abschnitt1' (Offset), die mit 'Abschnitt2' zusammengeführt (offset), mit verschiedenen Attributen  
  
 Der Inhalt von einem Abschnitt in eine andere zusammengeführt wurden, aber die Attribute von den beiden Abschnitten voneinander abweichen. Das Programm möglicherweise unerwartete Ergebnisse zurückgibt. Beispielsweise können Daten zu lesende nur jetzt in einem Abschnitt beschreibbar sein.  
  
 Um LNK4254 zu beheben, ändern Sie oder entfernen Sie die Mergeanforderung.  
  
 Beim X86 abzielen auf Computern und Windows CE-Ziele (ARM, MIPS, SH4 und Thumb) mit Visual C++ die. CRT-Abschnitt ist schreibgeschützt. Wenn der Code auf dem vorherigen Verhalten (. CRT-Abschnitte sind Lese-/Schreibzugriff), kann unerwartetes Verhalten angezeigt.  
  
 Weitere Informationen finden Sie unter  
  
-   [/ MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)  
  
-   [comment (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK4254 generiert.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```