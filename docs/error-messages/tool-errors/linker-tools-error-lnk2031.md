---
title: Linkertoolfehler Lnk2031 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2031
dev_langs: C++
helpviewer_keywords: LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a519b4241c9ffabaeeb387cc8e4997125d57781
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2031"></a>Linkertoolfehler LNK2031
für "ergänzter_Name" p/invoke generieren kann nicht ausgeführt werden. Aufrufkonvention, die in den Metadaten fehlt  
  
 Beim Versuch, eine systemeigene Funktion in einem reinen Image zu importieren, denken Sie daran, dass die impliziten Aufrufkonventionen zwischen systemeigenen und reinen Kompilierungen unterscheiden. Weitere Informationen zu reinen Bildern finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen Funktion, deren Aufrufkonvention implizit generiert [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel erstellt einen reinen Client, der die systemeigene Funktion verwendet. Allerdings die Aufrufkonvention unter **/CLR: pure** ist [__clrcall](../../cpp/clrcall.md). Im folgende Beispiel wird LNK2031 generiert.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie die systemeigene Funktion in einem reinen Image genutzt wird. Beachten Sie den expliziten **__cdecl** Spezifizierer der Aufrufkonvention.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```