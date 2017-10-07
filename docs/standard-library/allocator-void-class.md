---
title: Allocator&lt;void&gt;-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d816804e15e7a02edbe07f131529bf719039459f
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt;-Klasse
Eine Spezialisierung der Vorlagenklassenzuweisung zum Typ `void`, die die Typen definiert, die in diesem Kontext sinnvoll sind.  
  
## <a name="syntax"></a>Syntax  
  
```
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse spezialisiert explizit die Vorlagenklasse [allocator](../standard-library/allocator-class.md) für den Typ *void.* Dessen Konstruktoren und Zuweisungsoperator verhalten sich genauso wie für die Vorlagenklasse, aber sie definieren nur die folgenden Typen:  
  
- [const_pointer](../standard-library/allocator-class.md#const_pointer).  
  
- [pointer](../standard-library/allocator-class.md#pointer).  
  
- [value_type](../standard-library/allocator-class.md#value_type).  
  
- [rebind](../standard-library/allocator-class.md#rebind), eine geschachtelte Vorlagenklasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<memory>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




