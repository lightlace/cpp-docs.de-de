---
title: Compilerfehler C2393 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2393
dev_langs: C++
helpviewer_keywords: C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa9bc840894cf677e61c0247effcb875a2fdf2ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2393"></a>Compilerfehler C2393
'Symbol': anwendungsdomänenspezifisches Symbol kann nicht zugeordnet werden, in dem Segment "Segment"  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Die Verwendung von [Appdomain](../../cpp/appdomain.md) Variablen impliziert, dass Sie mit Kompilieren **/CLR: pure** oder **/CLR: safe**, und ein safe oder pure-Image darf keine Datensegmente enthalten.  
  
 Finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2393 generiert.  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```