---
title: is_trivially_copyable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: bf4387901e53dee51ae3c700a756358c63f8631a
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable-Klasse
Testet, ob der Typ ein trivialer Kopiertyp ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
struct is_trivially_copyable;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` ein trivialer Kopiertyp ist; andernfalls ist sie FALSE. Triviale Kopiertypen haben keine nicht trivialen Kopiervorgänge, Zuweisungsvorgänge oder Destruktoren. Im Allgemeinen wird ein Kopiervorgang als trivial angesehen, wenn er als eine bitweise Kopie implementiert werden kann. Integrierte Typen und Arrays trivialer Kopiertypen sind jeweils trivial kopierbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



