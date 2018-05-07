---
title: Compilerwarnung C4936 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcf9f32a4a1b1e43cb4bd69c754e3ae3a98bff3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4936"></a>Compilerwarnung C4936
__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert ist.  
  
 Ein `__declspec` -Modifizierer wurde verwendet, der `__declspec` -Modifizierer ist aber nur gültig, wenn er mit einer der [/clr](../../build/reference/clr-common-language-runtime-compilation.md) -Optionen kompiliert wird.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).  
  
 C4936 wird immer als Fehler ausgegeben.  Sie können C4936 mit dem [warning](../../preprocessor/warning.md) -Pragma deaktivieren.  
  
 Im folgenden Beispiel wird C4936 generiert:  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```