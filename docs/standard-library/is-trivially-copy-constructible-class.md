---
title: is_trivially_copy_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_copy_constructible
dev_langs: C++
helpviewer_keywords: is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e8029abe737aad771edf588e31b4a91d22fa092
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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



