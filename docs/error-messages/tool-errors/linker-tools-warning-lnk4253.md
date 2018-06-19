---
title: Linkertoolwarnung Lnk4253 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae4e88e1fe1434cd638d5c31cc8fd4d5c02c4de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301280"
---
# <a name="linker-tools-warning-lnk4253"></a>Linkertoolwarnung LNK4253
Abschnitt 'Abschnitt1' in 'Abschnitt2;' nicht zusammengeführt. bereits zusammengeführt in 'Abschnitt3'.  
  
 Der Linker erkannt mehrere Anforderungen in Konflikt stehende zusammenführen. Der Linker ignoriert eine Anforderung.  
  
 Ein **/MERGE** Option oder Richtlinie festgestellt wird und die `from` Abschnitt wurde bereits mit einem anderen Abschnitt aufgrund einer früheren zusammengeführt **/MERGE** Option oder -Direktive (oder aufgrund einer impliziten Zusammenführung der Linker).  
  
 Um LNK4253 zu beheben, entfernen Sie eines der Merge-Anforderungen.  
  
 Beim X86 abzielen auf Computern und Windows CE-Ziele (ARM, MIPS, SH4 und Thumb) mit Visual C++ die. CRT-Abschnitt ist jetzt schreibgeschützt. Wenn das vorherige Verhalten Ihr Code abhängt (. CRT-Abschnitte sind Lese-/Schreibzugriff), kann unerwartetes Verhalten angezeigt.  
  
 Weitere Informationen finden Sie unter  
  
-   [/MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)  
  
-   [comment (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Linker angewiesen, zum Zusammenführen der `.rdata` Abschnitt zweimal, aber in anderen Abschnitten. Im folgende Beispiel wird LNK4253 generiert.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```