---
title: stdext-Namespace | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 213b760a134a645a0b6552e4c3600fc4762b0bb2
ms.lasthandoff: 02/24/2017

---
# <a name="stdext-namespace"></a>stdext-Namespace
Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien sind zurzeit nicht Teil des ISO C++-Standards. Daher wurden diese Typen und Member aus dem `std` -Namespace in den `stdext`-Namespace verschoben, um dem C++-Standard zu entsprechen.  
  
 Beim Kompilieren mit der Standardoption [/Ze](../build/reference/za-ze-disable-language-extensions.md) gibt der Compiler eine Warnung für die Verwendung von `std` für Member der <hash_map>- und <hash_set>-Headerdateien aus. Verwenden Sie das [warning](../preprocessor/warning.md)-Pragma, um die Warnung zu deaktivieren.  
  
 Damit den Compiler bei der Verwendung von `std` für Member der <hash_map>- und <hash_set>-Headerdateien mit **/Ze** einen Fehler generiert, fügen Sie die folgende Anweisung vor dem Einbeziehen (#include) beliebiger Headerdateien der C++-Standardbibliothek hinzu.  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 Beim Kompilieren mit **/Za**generiert der Compiler einen Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)


