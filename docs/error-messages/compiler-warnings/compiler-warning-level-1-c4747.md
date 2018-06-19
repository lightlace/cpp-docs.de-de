---
title: Compilerwarnung (Stufe 1) C4747 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 203943f3741d07e278652a7032a6dcdcb305a384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285823"
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