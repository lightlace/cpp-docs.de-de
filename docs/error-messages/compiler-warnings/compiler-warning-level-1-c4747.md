---
title: Compilerwarnung (Stufe 1) C4747 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 094576ec19582b640ba0d4c57dfa34593177a267
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4747"></a>Compilerwarnung (Stufe 1) C4747
Aufrufen von verwalteten 'Einstiegspunkt': verwalteter Code kann nicht ausgeführt werden, unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und aufrufen, die aus der DLL-Einstiegspunkt wurde erreicht  
  
 Der Compiler hat einen (wahrscheinlichen) in MSIL kompilierte DLL-Einstiegspunkt gefunden.  Aufgrund potenzieller Probleme beim Laden einer DLL, deren Einstiegspunkt in MSIL kompiliert wurde, können Sie eine DLL-Einstiegspunktfunktion in MSIL kompiliert dringend abgeraten.  
  
 Weitere Informationen finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md) und [Linkertoolfehler LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Kompilieren Sie das Modul mit nicht **"/ CLR"**.  
  
2.  Markieren Sie die Einstiegspunktfunktion mit `#pragma unmanaged`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4747 generiert.  
  
```  
// C4747.cpp  
// compile with: /clr /c /W1  
// C4747 expected  
#include <windows.h>  
  
// Uncomment the following line to resolve.  
// #pragma unmanaged  
  
BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {  
   return TRUE;  
};  
```