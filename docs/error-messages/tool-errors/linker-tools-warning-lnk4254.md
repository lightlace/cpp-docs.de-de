---
title: Linkertoolwarnung Lnk4254 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb57882ab4269c06a53ed73fed2a9d6caf2f2c85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316893"
---
# <a name="linker-tools-warning-lnk4254"></a>Linkertoolwarnung LNK4254
Abschnitt 'Abschnitt1' (Offset), die mit 'Abschnitt2' zusammengeführt (offset), mit verschiedenen Attributen  
  
 Der Inhalt von einem Abschnitt in eine andere zusammengeführt wurden, aber die Attribute von den beiden Abschnitten voneinander abweichen. Das Programm möglicherweise unerwartete Ergebnisse zurückgibt. Beispielsweise können Daten zu lesende nur jetzt in einem Abschnitt beschreibbar sein.  
  
 Um LNK4254 zu beheben, ändern Sie oder entfernen Sie die Mergeanforderung.  
  
 Beim X86 abzielen auf Computern und Windows CE-Ziele (ARM, MIPS, SH4 und Thumb) mit Visual C++ die. CRT-Abschnitt ist schreibgeschützt. Wenn der Code auf dem vorherigen Verhalten (. CRT-Abschnitte sind Lese-/Schreibzugriff), kann unerwartetes Verhalten angezeigt.  
  
 Weitere Informationen finden Sie unter  
  
-   [/MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)  
  
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