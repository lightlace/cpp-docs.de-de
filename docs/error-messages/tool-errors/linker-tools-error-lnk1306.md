---
title: "Linkertoolfehler LNK1306"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1306"
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der DLL\-Einstiegspunkt Funktion kann nicht verwaltet sein; als systemeigen kompilieren  
  
 DllMain kann nicht zu MSIL kompiliert werden. DllMain muss zu systemeigenen Code kompiliert werden.  
  
 So beheben Sie diesen Fehler:  
  
-   Kompilieren Sie die Datei, die den Einstiegspunkt ohne **\/clr** enthält.  
  
-   Setzen Sie den Einstiegspunkt in einen `#pragma unmanaged`\-Abschnitt.  
  
-   Weitere Informationen finden Sie unter  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed, unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [Verhalten der Laufzeitbibliothek](../../build/run-time-library-behavior.md)  
  
## Beispiel  
 Im folgenden Beispiel wird LNK1306 generiert.  
  
```  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```