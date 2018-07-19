---
title: Compilerwarnung (Stufe 4) C4234 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4234
dev_langs:
- C++
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8d5b7a2999b77c0b34ee925f5dd85a0a27c63f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293516"
---
# <a name="compiler-warning-level-4-c4234"></a>Compilerwarnung (Stufe 4) C4234
nicht dem Standard entsprechende Erweiterung: ' Schlüsselwort ' für die zukünftige Verwendung reserviert  
  
 Der Compiler implementiert nicht noch das Schlüsselwort, das Sie verwendet.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md). Geben Sie beispielsweise Folgendes ein, um C4234 in eine Warnung der Stufe 4 Stellen,  
  
```  
#pragma warning(2:4234)  
```  
  
 in der Quellcodedatei.