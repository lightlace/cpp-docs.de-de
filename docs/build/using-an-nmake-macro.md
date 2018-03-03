---
title: Verwenden eines NMAKE-Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc5c6c8851654b1a767967ffc900886d75521130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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