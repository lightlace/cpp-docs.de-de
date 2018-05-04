---
title: Verwenden eines NMAKE-Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6bf098a3723aa7b067b8192bf503975998e4e98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="using-an-nmake-macro"></a>Verwenden eines NMAKE-Makros
Wenn ein Makro verwenden möchten, schließen Sie seinen Namen in Klammern, die ein Dollarzeichen ($) vorangestellt sind, wie folgt.  
  
## <a name="syntax"></a>Syntax  
  
```  
$(macroname)  
```  
  
## <a name="remarks"></a>Hinweise  
 Es sind keine Leerzeichen zulässig. Die Klammern sind optional, wenn *Macroname* ist ein einzelnes Zeichen. Die parameterdefinitions-Zeichenfolge ersetzt $(*Macroname*); ein nicht definiertes Makro wird durch eine null-Zeichenfolge ersetzt.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Makroersetzung](../build/macro-substitution.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und NMAKE](../build/macros-and-nmake.md)