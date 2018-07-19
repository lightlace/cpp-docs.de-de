---
title: Linkertoolfehler Lnk1306 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb340a4c28f94f18e0c4b65bea8749394e002bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300497"
---
# <a name="linker-tools-error-lnk1306"></a>Linkertoolfehler LNK1306  
  
> DLL-Einstiegspunktfunktion kann nicht verwaltet werden; Kompilieren in systemeigenen  
  
`DllMain` kann nicht in MSIL kompiliert werden; Sie müssen in den einheitlichen kompiliert werden.  
  
Um dieses Problem zu beheben.  
  
-   Kompilieren Sie die Datei, die den Einstiegspunkt ohne enthält **"/ CLR"**.  
  
-   Fügen Sie den Einstiegspunkt in eine `#pragma unmanaged` Abschnitt.  
  
Weitere Informationen finden Sie unter:  
  
-   [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed, unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](../../build/run-time-library-behavior.md)  
  
## <a name="example"></a>Beispiel  
  
Im folgenden Beispiel wird LNK1306 generiert.  
  
```cpp  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```  
  
Um dieses Problem zu beheben, verwenden Sie nicht die Option "/ CLR", kompilieren Sie diese Datei, oder verwenden Sie eine `#pragma` Direktive, um die Definition der Eintrag Punkt in einem nicht verwalteten Abschnitt zusätzlich belasten, da in diesem Beispiel gezeigt:  
  
```cpp  
// LNK1306fix.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
#include <windows.h>  
#pragma managed(push, off)  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
#pragma managed(pop)  
```  
