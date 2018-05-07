---
title: Linkertoolfehler Lnk2028 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7347e8edda7ad8b317d4e6e02dfc9345ac76f269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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