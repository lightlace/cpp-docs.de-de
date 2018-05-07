---
title: Compilerwarnung (Stufe 1) C4627 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcde9e6707465fd95dbcb10e073a852624f0de0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4627"></a>Compilerwarnung (Stufe 1) C4627
"\<Bezeichner >": bei der Suche nach Verwendung des vorkompilierten Headers übersprungen  
  
 Bei der Suche nach dem Ort, in dem ein vorkompilierter Header verwendet wird, der Compiler hat festgestellt ein `#include` Richtlinie für die  *\<Bezeichner >* Includedatei. Der Compiler ignoriert die `#include` Richtlinie, gibt aber die Warnung **C4627** , wenn der vorkompilierte Header nicht bereits enthält die  *\<Bezeichner >* Includedatei.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)