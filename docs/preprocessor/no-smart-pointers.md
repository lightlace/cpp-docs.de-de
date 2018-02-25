---
title: No_smart_pointers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_search_pointers
dev_langs:
- C++
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d1e06265771a163375d1095b4c481aa6d7d250f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C++-spezifisch**  
  
 Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_smart_pointers  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie `#import` verwenden, rufen Sie standardmäßig die Deklaration eines intelligenten Zeigers für alle Schnittstellen in der Typbibliothek ab. Diese intelligenten Zeiger sind vom Typ [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md).  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)