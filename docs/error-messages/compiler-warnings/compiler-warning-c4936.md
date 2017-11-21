---
title: Compilerwarnung C4936 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4936
dev_langs: C++
helpviewer_keywords: C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4342c749c5db4d66f206209a146ad7d7aef7041
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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