---
title: Verwenden eines NMAKE-Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9893e7ec1ba29b4b5ed2ccb569a135f44b2ed47f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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