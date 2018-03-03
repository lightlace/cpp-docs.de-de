---
title: Compilerwarnung (Stufe 1) C4627 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66d199b8dede21f94a963113341eb6426f66a807
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4627"></a>Compilerwarnung (Stufe 1) C4627
"\<Bezeichner >": bei der Suche nach Verwendung des vorkompilierten Headers übersprungen  
  
 Bei der Suche nach dem Ort, in dem ein vorkompilierter Header verwendet wird, der Compiler hat festgestellt ein `#include` Richtlinie für die  *\<Bezeichner >* Includedatei. Der Compiler ignoriert die `#include` Richtlinie, gibt aber die Warnung **C4627** , wenn der vorkompilierte Header nicht bereits enthält die  *\<Bezeichner >* Includedatei.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)