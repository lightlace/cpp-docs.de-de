---
title: Makroersetzung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c2ea7a2509e58cfd4da163cc76c018d06c244fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="macro-substitution"></a>Makroersetzung
Wenn *Macroname* aufgerufen wird, jedem Vorkommen von *string1* Zeichenfolge wird in der Definition durch ersetzt *Zeichenfolge2*.  
  
## <a name="syntax"></a>Syntax  
  
```  
$(macroname:string1=string2)  
```  
  
## <a name="remarks"></a>Hinweise  
 Makroersetzung wird die Groß-/Kleinschreibung beachtet und Literal; *string1* und *Zeichenfolge2* Makros kann nicht aufgerufen werden. Ersetzung die ursprüngliche Definition nicht geändert. Sie können Text in vordefinierten Makros außer ersetzen [ $$@ ](../build/filename-macros.md).  
  
 Keine Leerzeichen oder Tabstopps vor dem Doppelpunkt befinden; nach dem Doppelpunkt werden als Literal interpretiert. Wenn *Zeichenfolge2* null ist, alle Vorkommen von *string1* parameterdefinitions-Zeichenfolge für das Makro gelöscht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines NMAKE-Makros](../build/using-an-nmake-macro.md)