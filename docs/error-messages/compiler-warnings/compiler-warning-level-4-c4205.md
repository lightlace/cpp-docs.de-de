---
title: Compilerwarnung (Stufe 4) C4205 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4205
dev_langs:
- C++
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd40764ea6a37acf11a43fb08ffad80e4c1bd8c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4205"></a>Compilerwarnung (Stufe 4) C4205
nicht dem Standard entsprechende Erweiterung: statische Funktionsdeklaration im Gültigkeitsbereich der Funktion  
  
 Mit Microsoft-Erweiterungen (/ Ze) **statische** Funktionen können innerhalb einer anderen Funktion deklariert werden. Die Funktion erhält die globalen Gültigkeitsbereich.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 Solche Initialisierungen sind ungültig, ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)).