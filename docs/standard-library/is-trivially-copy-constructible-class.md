---
title: is_trivially_copy_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
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
ms.openlocfilehash: 3c99808198c527fb60105d9a2d5629d177da5461
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible-Klasse
Testet, ob der Typ einen trivialen Kopierkonstruktor aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
struct is_trivially_copy_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `T` Typ eine Klasse ist, die einen trivialen Kopierkonstruktor aufweist; andernfalls „false“.  
  
 Ein Kopierkonstruktor für eine Klasse `T` ist trivial, wenn er implizit deklariert wurde. Die Klasse `T` verfügt über keine virtuellen Funktionen oder Basen und alle direkten Basen der Klasse `T` haben triviale Kopierkonstruktoren. Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Kopierkonstruktoren und die Klassen aller nicht statischen Datenmember vom Typ „array“ der Klasse haben triviale Kopierkonstruktoren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




