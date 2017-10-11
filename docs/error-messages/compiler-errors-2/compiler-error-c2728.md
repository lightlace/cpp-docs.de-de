---
title: Compilerfehler Fehler C2728 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2728
dev_langs:
- C++
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f83665f1f2b388ac751dd4fd4aec2f75e8651a3
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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

