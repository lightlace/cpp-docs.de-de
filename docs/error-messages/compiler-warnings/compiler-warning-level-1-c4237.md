---
title: Compilerwarnung (Stufe 1) C4237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4237
dev_langs:
- C++
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dfefb2dc7dd04f2334b2b7d222153d5ee351ae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277578"
---
# <a name="compiler-warning-level-1-c4237"></a>Compilerwarnung (Stufe 1) C4237
' Schlüsselwort ' wird noch nicht unterstützt, aber für die zukünftige Verwendung reserviert  
  
 Ein Schlüsselwort in der C++-Spezifikation ist nicht in der Visual C++-Compiler implementiert, aber das Schlüsselwort ist nicht als ein benutzerdefiniertes Symbol verfügbar.  
  
 Im folgenden Beispiel wird C4237 generiert:  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```