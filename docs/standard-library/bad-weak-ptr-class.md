---
title: bad_weak_ptr-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: memory/std::bad_weak_ptr
dev_langs: C++
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a91aa087611c9e83146a8ed667dbe582c091f4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="badweakptr-class"></a>bad_weak_ptr-Klasse
Meldet eine ungültige weak_ptr-Ausnahme.  
  
## <a name="syntax"></a>Syntax  
  
```  
class bad_weak_ptr : public std::exception 
 {  
public:  
    bad_weak_ptr();
    const char *what() throw();
 };  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse beschreibt eine Ausnahme, die von dem [shared_ptr-Klasse](../standard-library/shared-ptr-class.md)-Konstruktor ausgelöst werden kann, der ein Argument des Typs [weak_ptr-Klasse](../standard-library/weak-ptr-class.md) verwendet. Die Memberfunktion `what` gibt `"bad_weak_ptr"` zurück.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__memory__bad_weak_ptr.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
 
int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired   
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```  
  
```Output  
bad weak pointer  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<memory>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [weak_ptr-Klasse](../standard-library/weak-ptr-class.md)
