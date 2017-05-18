---
title: treat_as_floating_point-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
dev_langs:
- C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9d9e6b0b281fb97475b0c23acb4bf7d0fc391a52
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point-Struktur
Gibt an, ob `Rep` als Gleitkommatyp behandelt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## <a name="remarks"></a>Hinweise  
 `Rep` kann nur als Gleitkommatyp behandelt werden, wenn die Spezialisierung `treat_as_floating_point<Rep>` von [true_type](../standard-library/type-traits-typedefs.md#true_type) abgeleitet wird. Die Vorlagenklasse kann für einen benutzerdefinierten Typ abgeleitet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Chrono >  
  
 **Namespace:** std::chrono  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


