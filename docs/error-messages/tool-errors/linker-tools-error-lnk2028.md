---
title: Linkertoolfehler Lnk2028 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7441dcd893e3e814d738f228d002a947e7f43c8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2028"></a>Linkertoolfehler LNK2028
Verweis auf "exportierte_Funktion" (ergänzter_Name) in der Funktion "Funktion_mit_Funktionsaufruf" (ergänzter_Name) auf die verwiesen wird.  
  
 Beim Versuch, eine systemeigene Funktion in einem reinen Image zu importieren, denken Sie daran, dass die impliziten Aufrufkonventionen zwischen systemeigenen und reinen Kompilierungen unterscheiden.  
  
## <a name="example"></a>Beispiel  
 In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen Funktion, deren Aufrufkonvention implizit generiert [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel erstellt einen reinen Client, der die systemeigene Funktion verwendet. Allerdings die Aufrufkonvention unter **/CLR: pure** ist [__clrcall](../../cpp/clrcall.md). Im folgende Beispiel wird LNK2028 generiert.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```