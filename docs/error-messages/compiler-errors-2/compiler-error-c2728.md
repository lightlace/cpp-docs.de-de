---
title: "Compilerfehler C2728"
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
  - "C2728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2728"
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : Ein systemeigenes Array darf diesen Typ nicht enthalten.  
  
 Erstellung von Arraysyntax verwendet, um ein Array von verwalteten oder WinRT\-Objekten zu erstellen.  Sie können kein Array von verwalteten oder WinRT\-Objekten mit systemeigener Array\-Syntax erstellen.  
  
 Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C2728 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
  
 Ein [\_\_nogc](../../misc/nogc.md) Array kann nicht vom Typ [\_\_gc](../../misc/gc.md) sein.  
  
 Im folgenden Beispiel wird C2728 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2728_b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
int main() {  
   int __gc* arr __nogc[5];   // C2728  
  
   // try the following line instead  
   int arr2 __gc[];  
}  
```