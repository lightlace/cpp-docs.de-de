---
title: Compilerwarnung (Stufe 4) C4232 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4232
dev_langs:
- C++
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 093f9eeeb27b402b58f3d53ae34952c34dca3779
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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