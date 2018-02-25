---
title: is_trivially_copy_assignable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8fe1f72d609c30dbd7abf9fb0d0ca6803d90a29
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable-Klasse
Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_trivially_copy_assignable;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der `T`-Typ eine Klasse ist, die einen Kopierzuweisungsoperator aufweist; andernfalls FALSE.  
  
 Ein Zuweisungskonstruktor für eine Klasse `T` ist trivial, wenn er implizit angegeben ist. Die Klasse `T` verfügt über keine virtuellen Funktionen und die Klasse `T` hat keine virtuellen Basen. Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Zuweisungsoperatoren und die Klassen aller nicht statischen Datenmember vom Typ „array“ der Klasse haben triviale Zuweisungsoperatoren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



