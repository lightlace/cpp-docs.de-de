---
title: Compilerwarnung (Stufe 1) C4532 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4532
dev_langs: C++
helpviewer_keywords: C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44aae61190b20bf1ef93b586c02e88837d487324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4532"></a>Compilerwarnung (Stufe 1) C4532
"continue": Herausspringen aus __finally/finally-Block ist ein nicht definiertes Verhalten während der Abbruchbehandlung  
  
 Der Compiler hat festgestellt, eines der folgenden Schlüsselwörter:  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 verursacht einen Sprung aus einem [__finally](../../cpp/try-finally-statement.md) oder [schließlich](../../dotnet/finally.md) Block bei nicht ordnungsgemäßer Beendigung.  
  
 Wenn eine Ausnahme auftritt, und zwar während der Ausführung der Beendigungshandler im Stapel entladen wird (der `__finally` oder finally-Blöcke), und Code springt von einer `__finally` blockieren, bevor Sie die `__finally` blockieren endet, das Verhalten nicht definiert ist. Steuerelement möglicherweise nicht an den entladenen Code zurück, damit die Ausnahme möglicherweise nicht ordnungsgemäß behandelt werden.  
  
 Wenn Sie von springen müssen eine **__finally** blockieren, prüfen Sie zunächst für die nicht ordnungsgemäße Beendigung.  
  
 Im folgende Beispiel wird C4532 generiert. einfach die Warnungen auflösen-sprunganweisungen kommentieren.  
  
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