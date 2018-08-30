---
title: Compilerwarnung (Stufe 4) C4242 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 623183e5ee54c995d624f47461c724ee8f4befae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217397"
---
# <a name="compiler-warning-level-4-c4242"></a>Compilerwarnung (Stufe 4) C4242
'Bezeichner': Konvertierung von 'type1' in 'type2', möglicher Datenverlust  
  
 Die Typen unterscheiden. Typkonvertierung kann zu Datenverlust führen. Der Compiler stellt die typkonvertierung.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Weitere Informationen über C4242, finden Sie unter [Häufige Compilerfehler](/windows/desktop/WinProg64/common-compiler-errors).  
  
 Im folgende Beispiel wird die C4242 generiert:  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```