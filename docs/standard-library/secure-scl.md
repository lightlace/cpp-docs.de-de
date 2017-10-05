---
title: _SECURE_SCL | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 191cdecc193466982bc0808d517b7ad4d53c4b8d
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="securescl"></a>_SECURE_SCL
  
Ersetzt durch [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), dieses Makro definiert, ob [Überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert sind. Standardmäßig sind „Überprüfte Iteratoren“ in Debugbuilds aktiviert und in Verkaufsversionen deaktiviert.  
  
> [!IMPORTANT]
> Die direkte Verwendung des `_SECURE_SCL`-Makros ist veraltet. Verwenden Sie stattdessen `_ITERATOR_DEBUG_LEVEL`, um die Einstellungen von überprüften Iteratoren zu steuern. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Hinweise  
  
Wenn überprüfte Iteratoren aktiviert sind, verursacht die unsichere Verwendung einen Laufzeitfehler und das Programm wird beendet. Um überprüfte Iteratoren zu aktivieren, legen Sie `_ITERATOR_DEBUG_LEVEL` auf 1 oder 2 fest. Dies entspricht der `_SECURE_SCL`-Einstellung 1 oder „Aktiviert“:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
Um überprüfte Iteratoren zu deaktivieren, legen Sie `_ITERATOR_DEBUG_LEVEL` auf 0 fest. Dies entspricht der `_SECURE_SCL`-Einstellung 0 oder „Deaktiviert“:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
Informationen über das Deaktivieren von Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="see-also"></a>Siehe auch  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[Überprüfte Iteratoren](../standard-library/checked-iterators.md)   
[Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)   
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)


