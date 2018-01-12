---
title: _HAS_ITERATOR_DEBUGGING | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _HAS_ITERATOR_DEBUGGING
dev_langs: C++
helpviewer_keywords: _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c680338fa84fa0f00e01ea4612d07c851570a36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING  
  
Durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) ersetzt, definiert dieses Makro, ob die Iteratordebugfunktion in einem Debugbuild aktiviert ist. Standardmäßig ist das Iteratordebuggen in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert. Weitere Informationen finden Sie unter [Debugiterator-Unterstützung](../standard-library/debug-iterator-support.md).  
  
> [!IMPORTANT]
> Die direkte Verwendung des `_HAS_ITERATOR_DEBUGGING`-Makros ist veraltet. Verwenden Sie stattdessen `_ITERATOR_DEBUG_LEVEL`, um Iteratordebugeinstellungen zu steuern. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Hinweise  
Legen Sie in Debugbuilds `_ITERATOR_DEBUG_LEVEL` auf 2 fest, um das Iteratordebuggen zu aktivieren. Dies entspricht einer `_HAS_ITERATOR_DEBUGGING`-Einstellung von 1 oder aktiviert:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 2  
```  
  
`_ITERATOR_DEBUG_LEVEL` kann in Verkaufsversionen nicht auf 2 festgelegt werden (und `_HAS_ITERATOR_DEBUGGING` nicht auf 1).  
  
Legen Sie zum Deaktivieren des Debuggens der Iteratoren `_ITERATOR_DEBUG_LEVEL` auf 0 oder 1 in Debugbuilds. Dies entspricht einer `_HAS_ITERATOR_DEBUGGING`-Einstellung von 0 oder deaktiviert:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
## <a name="see-also"></a>Siehe auch  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
 [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)   
 [Überprüfte Iteratoren](../standard-library/checked-iterators.md)   
 [Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)
