---
title: unchecked_array_iterator-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unchecked_array_iterator
- stdext::unchecked_array_iterator
dev_langs:
- C++
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 850f1eced3ef5354a382d392c83b8180a18b4dfb
ms.lasthandoff: 02/24/2017

---
# <a name="uncheckedarrayiterator-class"></a>unchecked_array_iterator-Klasse
Die `unchecked_array_iterator`-Klasse ermöglicht es Ihnen, ein Array oder einen Zeiger in einen deaktivierten Iterator zu umschließen. Verwenden Sie diese Klasse (mithilfe der [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)-Funktion) als Wrapper für unformatierte Zeiger oder Arrays als gezielte Methode zum Verwalten von Warnungen zu nicht aktivierten Zeigern, anstatt diese Warnungen allgemein zu deaktivieren. Verwenden Sie wenn möglich die aktivierte Version [checked_array_iterator](../standard-library/checked-array-iterator-class.md) dieser Klasse.  
  
> [!NOTE]
>  Bei dieser Klasse handelt es sich um eine Microsoft-Erweiterung der C++-Standardbibliothek. Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C++-Standardbuildumgebungen übertragbar, die die Microsoft-Erweiterung nicht unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Iterator>  
class unchecked_array_iterator;
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird im [stdext](../standard-library/stdext-namespace.md)-Namespace definiert.  
  
 Das ist die nicht aktivierte Version der [checked_array_iterator-Klasse](../standard-library/checked-array-iterator-class.md), die dieselben Überladungen und Member unterstützt. Weitere Informationen zur aktivierten Iteratorfunktion mit Codebeispielen finden Sie unter [Checked Iterators (Aktivierte Iteratoren)](../standard-library/checked-iterators.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Siehe auch  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ Standard Library Reference (C++-Standardbibliotheksreferenz)](../standard-library/cpp-standard-library-reference.md)




