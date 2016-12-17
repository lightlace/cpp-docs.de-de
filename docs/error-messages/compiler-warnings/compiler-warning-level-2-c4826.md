---
title: "Compilerwarnung (Stufe 2) C4826"
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
  - "C4826"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4826"
ms.assetid: 286f5c1d-8c14-43f7-aaa6-a891db2fdc64
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4826
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Konvertierung von 'Typ1' in 'Typ2' ist signaturerweitert.Dies kann zu unerwartetem Laufzeitverhalten führen.  
  
 Diese Warnung wird angezeigt, wenn der Compiler beim Umwandeln eines 32\-Bit\-Zeigers in eine 64\-Bit\-Variable eine Vorzeichenerweiterung ausgeführt hat.  
  
 Wenn die Erweiterung auf einem Windows\-HANDLE\-Typ ausgeführt wurde, können Sie diese Warnung ignorieren.  Wenn die Erweiterung auf einem Zeigertyp ausgeführt wurde, sollten Sie den Code so anpassen, dass die Vorzeichenerweiterung verhindert wird \(siehe Beispiel unten\).  
  
 C4826 ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4826 generiert.  
  
```  
// C4826.cpp  
// compile with: /W2 /c  
#include <windows.h>  
#pragma warning(default: 4826)  
  
void * __ptr64 F1 (void * __ptr32 P ) {  
   return (void * __ptr64)P;   // C4826  
   // try the following line instead  
   // return (void * __ptr64)(ULONGLONG)(ULONG)P;  
}  
  
void * __ptr64 F2 ( void * P ) {  
   return (void * __ptr64)P;   // C4826  
   // try the following line instead  
   // return (void * __ptr64)(ULONGLONG)(ULONG)P;  
}  
  
unsigned __int64 F3r ( void * P ) {  
   return (unsigned __int64)P;   // C4826  
   // try the following line instead  
   // return (unsigned __int64)(ULONGLONG)(ULONG)P;  
}  
```