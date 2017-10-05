---
title: is_standard_layout-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 41d0472a031904fbb40d381aa6113da17feb3e1b
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="isstandardlayout-class"></a>is_standard_layout-Klasse
Testet, ob der Typ ein Standardlayout ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_standard_layout;
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Ty`|Der abzufragende Typ.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz dieses Typenprädikats gibt „true“ aus, wenn der Typ `Ty` eine Klasse ist, die über ein Standardlayout der Memberobjekte im Arbeitsspeicher verfügt; ansonsten wird „false“ ausgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




