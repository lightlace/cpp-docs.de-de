---
title: is_trivially_move_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17e564e89134a858eabf09b3f208461892da3fb3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible-Klasse
Testet, ob der Typ einen trivialen Bewegungskonstruktor aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_trivially_move_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der `Ty` Typ eine Klasse ist, die einen trivialen Bewegungskonstruktor aufweist; andernfalls FALSE.  
  
 Ein Bewegungskonstruktor für eine `Ty`-Klasse ist trivial, wenn:  
  
 Er wird implizit deklariert.  
  
 die Parametertypen entsprechen den einer impliziten Deklaration  
  
 die `Ty`-Klasse hat keine virtuellen Funktionen  
  
 die `Ty`-Klasse hat keine virtuellen Basen  
  
 die Klasse verfügt über keine flüchtigen nicht statischen Datenmember  
  
 alle direkten Basisklassen der `Ty`-Klasse weisen triviale Bewegungskonstruktoren auf  
  
 die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Bewegungskonstruktoren  
  
 die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Bewegungskonstruktoren  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



