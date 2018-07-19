---
title: Compilerwarnung (Stufe 4) C4001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc728fa5c66fb4b42c8fe4a785f36048ffbaed4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292658"
---
# <a name="compiler-warning-level-4-c4001"></a>Compilerwarnung (Stufe 4) C4001
nicht dem Standard entsprechende Erweiterung "einzeiliger Kommentar" wurde verwendet.  

> [!NOTE] 
> Diese Warnung wird in Visual Studio 2017 Version 15.5 entfernt, da einzeilige Kommentare in C99 eine Standardeinstellung darstellen.
  
 Einzeilige Kommentare sind in C++ standard und standard in C99 C ab. Strikte ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)), C-Dateien, die einzeilige Kommentare, enthalten die Warnung C4001 aufgrund der Verwendung einer nicht dem Standard entsprechende Erweiterung. Da einzeilige Kommentare standard in C++ sind, erzeugen C-Dateien, die einzeilige Kommentare enthält keine C4001 beim Kompilieren mit Microsoft-Erweiterungen (/ Ze).  
  
## <a name="example"></a>Beispiel  
 Um die Warnung zu deaktivieren, kommentieren [#pragma warning(Disable:4001) aus](../../preprocessor/warning.md).  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```