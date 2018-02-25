---
title: is_error_condition_enum-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f92a07a904ae80fb56e2cf21114bb79506dfa11
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum-Klasse
Stellt ein Typprädikat dar, das auf die [error_code](../standard-library/error-condition-class.md)-Enumeration testet.  
  
## <a name="syntax"></a>Syntax  
  
```
template <_Enum>
class is_error_condition_enum;
```  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz dieses [Typprädikats](../standard-library/type-traits.md) ist TRUE, wenn der Typ `_Enum` ein geeigneter Enumerationswert für das Speichern in einem Objekt vom Typ `error_condition` ist.  
  
 Es ist zulässig, Spezialisierungen zu dieser Art für benutzerdefinierte Typen hinzuzufügen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<system_error>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)



