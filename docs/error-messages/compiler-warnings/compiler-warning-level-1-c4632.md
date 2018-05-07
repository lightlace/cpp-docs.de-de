---
title: Compilerwarnung (Stufe 1) C4632 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4632
dev_langs:
- C++
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4aa05b039d3d4a8cddcc607861ea27e9591cfc29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4632"></a>Compilerwarnung (Stufe 1) C4632
XML-Dokumentkommentar: Datei - Zugriff verweigert: Grund  
  
 Der Pfad zur XDC-Datei (`file`) war ungültig, und keine XDC-Datei erstellt.  
  
 Im folgenden Beispiel wird C4632 generiert:  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```