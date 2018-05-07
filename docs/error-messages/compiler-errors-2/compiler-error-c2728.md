---
title: Compilerfehler Fehler C2728 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2728
dev_langs:
- C++
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e954ba38efc2e1ef7bc4b203c8b54876f7aae0ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2728"></a>Compilerfehler Fehler C2728
'type' : Ein systemeigenes Array darf diesen Typ nicht enthalten.  
  
 Erstellung von Arraysyntax verwendet, um ein Array von verwalteten oder WinRT-Objekten zu erstellen. Sie können kein Array von verwalteten oder WinRT-Objekten mit systemeigener Array-Syntax erstellen.  
  
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
