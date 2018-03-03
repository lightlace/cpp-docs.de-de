---
title: Compilerwarnung (Stufe 4) C4232 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4232
dev_langs:
- C++
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0b8725ca2a7ee6c5f512559eecdb6b01ac4c6a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4232"></a>Compilerwarnung (Stufe 4) C4232
nicht dem Standard entsprechende Erweiterung: 'Bezeichner': Adresse von Dllimport 'Dllimport' ist nicht statisch, Identität nicht garantiert.  
  
 Sie können unter Microsoft-Erweiterungen (/ Ze), einen nicht statischen Wert geben, wie mit der Adresse einer Funktion deklariert die **Dllimport** Modifizierer. ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)), dies verursacht einen Fehler.  
  
 Im folgenden Beispiel wird C4232 generiert:  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```