---
title: Definieren eines NMAKE-Makros | Microsoft Docs
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
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96799bbd10d442c50d66ac4e84169864b9b989ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="defining-an-nmake-macro"></a>Definieren eines NMAKE-Makros
## <a name="syntax"></a>Syntax  
  
```  
  
macroname=string  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Macroname* ist eine Kombination aus Buchstaben, Ziffern und Unterstriche (_) bis zu 1.024 Zeichen und Fall beachtet wird. Die *Macroname* kann ein aufgerufenes Makro enthalten. Wenn *Macroname* besteht ausschließlich aus einem aufgerufenen Makro darf nicht das Makro aufgerufen wurde null oder nicht definiert sein.  
  
 Die `string` kann eine beliebige Sequenz von NULL oder mehr Zeichen sein. Eine null-Zeichenfolge enthält 0 (null) Zeichen oder nur Leerzeichen oder Tabstopps. Die `string` kann einen Makroaufruf enthalten.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Sonderzeichen in Makros](../build/special-characters-in-macros.md)  
  
 [NULL und Undefinierte Makros](../build/null-and-undefined-macros.md)  
  
 [WHERE Definieren von Makros](../build/where-to-define-macros.md)  
  
 [Rangfolge bei Makrodefinitionen](../build/precedence-in-macro-definitions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und NMAKE](../build/macros-and-nmake.md)