---
title: alignment_of-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::alignment_of
dev_langs: C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de94e34dd0e00a2902454b4ab41f1790c194b6dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alignmentof-class"></a>alignment_of-Klasse
Ruft die Ausrichtung des angegebenen Typs ab. Diese Struktur wird in Bezug auf [alignof](../cpp/alignof-and-alignas-cpp.md) implementiert. Verwenden Sie `alignof` direkt, wenn Sie einen Ausrichtungswert einfach abfragen müssen. Verwenden Sie „alignment_of“, wenn Sie eine integrale Konstante benötigen, beispielsweise beim Versenden eines Tags.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct alignment_of;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Die Typabfrage hält den Wert der Ausrichtung des Typs `Ty`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [aligned_storage-Klasse](../standard-library/aligned-storage-class.md)
