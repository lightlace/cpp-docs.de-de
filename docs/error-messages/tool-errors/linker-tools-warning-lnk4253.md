---
title: Linkertoolwarnung Lnk4253 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4253
dev_langs: C++
helpviewer_keywords: LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d1142544852980b8bd1d543783a9ffdf3361879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4253"></a>Linkertoolwarnung LNK4253
Abschnitt 'Abschnitt1' in 'Abschnitt2;' nicht zusammengeführt. bereits zusammengeführt in 'Abschnitt3'.  
  
 Der Linker erkannt mehrere Anforderungen in Konflikt stehende zusammenführen. Der Linker ignoriert eine Anforderung.  
  
 Ein **/MERGE** Option oder Richtlinie festgestellt wird und die `from` Abschnitt wurde bereits mit einem anderen Abschnitt aufgrund einer früheren zusammengeführt **/MERGE** Option oder -Direktive (oder aufgrund einer impliziten Zusammenführung der Linker).  
  
 Um LNK4253 zu beheben, entfernen Sie eines der Merge-Anforderungen.  
  
 Beim X86 abzielen auf Computern und Windows CE-Ziele (ARM, MIPS, SH4 und Thumb) mit Visual C++ die. CRT-Abschnitt ist jetzt schreibgeschützt. Wenn das vorherige Verhalten Ihr Code abhängt (. CRT-Abschnitte sind Lese-/Schreibzugriff), kann unerwartetes Verhalten angezeigt.  
  
 Weitere Informationen finden Sie unter  
  
-   [/ MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)  
  
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