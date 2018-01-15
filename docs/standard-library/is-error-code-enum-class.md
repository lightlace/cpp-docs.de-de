---
title: is_error_code_enum-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::is_error_code_enum
dev_langs: C++
helpviewer_keywords: is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56f402c938d3e481e9d859d66f383b5f8886df61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum-Klasse
Stellt ein Typprädikat dar, das auf die [error_code](../standard-library/error-code-class.md)-Enumeration testet.  
  
## <a name="syntax"></a>Syntax  
  
```
template <_Enum>
class is_error_code_enum;
```  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz dieses [Typprädikats](../standard-library/type-traits.md) ist TRUE, wenn der Typ `_Enum` ein geeigneter Enumerationswert für das Speichern in einem Objekt vom Typ `error_code` ist.  
  
 Es ist zulässig, Spezialisierungen zu dieser Art für benutzerdefinierte Typen hinzuzufügen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<system_error>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)



