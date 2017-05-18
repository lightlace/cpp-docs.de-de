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
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a435eef7397eb98ca500be1c99e92efcb55c8be6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4627"></a>Compilerwarnung (Stufe 1) C4627
"\<Bezeichner >": bei der Suche nach Verwendung des vorkompilierten Headers übersprungen  
  
 Bei der Suche nach dem Ort, in dem ein vorkompilierter Header verwendet wird, der Compiler hat festgestellt ein `#include` Richtlinie für die *\<Bezeichner >* Includedatei. Der Compiler ignoriert die `#include` Richtlinie, gibt aber die Warnung **C4627** , wenn der vorkompilierte Header nicht bereits enthält die *\<Bezeichner >* Includedatei.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)
