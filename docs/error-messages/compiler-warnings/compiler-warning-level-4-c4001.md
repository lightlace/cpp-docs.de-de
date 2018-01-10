---
title: Compilerwarnung (Stufe 4) C4001 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4001
dev_langs: C++
helpviewer_keywords: C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3b5c3d82bef81ee84514b39a0ce8ab07ad6e6c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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