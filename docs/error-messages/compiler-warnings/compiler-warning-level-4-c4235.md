---
title: Compilerwarnung (Stufe 4) C4235 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc63640bc58caefa281b9207b9796ffdf387a7a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4235"></a>Compilerwarnung (Stufe 4) C4235
Nicht dem Standard entsprechende Erweiterung: Das Schlüsselwort 'Schlüsselwort' wird für diese Architektur nicht unterstützt  
  
 Das von Ihnen verwendete Schlüsselwort wird vom Compiler nicht unterstützt.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md). Um C4235 beispielsweise in eine Warnung der Stufe 2 umzuwandeln, verwenden Sie folgende Codezeile  
  
```  
#pragma warning(2:4235)  
```  
  
 in der Quellcodedatei.