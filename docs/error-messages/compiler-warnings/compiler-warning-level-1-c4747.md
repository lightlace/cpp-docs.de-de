---
title: "Compilerwarnung (Stufe 1) C4747 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4747"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4747"
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 1) C4747
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aufruf von 'Einstiegspunkt' \(verwaltet\): Verwalteter Code darf nicht unter der Loadersperre, einschließlich des DLL\-Einstiegspunkts und Aufrufen, die vom DLL\-Einstiegspunkt eingehen, ausgeführt werden.  
  
 Vom Compiler wird ein \(möglicher\) zu MSIL kompilierter DLL\-Einstiegspunkt festgestellt.  Aufgrund möglicher Probleme beim Laden einer DLL, deren Einstiegspunkt zu MSIL kompiliert wurde, wird dringend davon abgeraten, einen DLL\-Einstiegspunkt zu MSIL zu kompilieren.  
  
 Weitere Informationen finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md) und [Linkertoolfehler LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).  
  
### So beheben Sie diesen Fehler  
  
1.  Kompilieren Sie das Modul nicht mit **\/clr**.  
  
2.  Markieren Sie die Einstiegspunktfunktion mit `#pragma unmanaged`.  
  
## Beispiel  
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