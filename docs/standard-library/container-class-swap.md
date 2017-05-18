---
title: Containerklasse::swap | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 33ec601dcc8d32b85c2c38ed3fc5a07842a056fc
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="container-classswap"></a>Container-Klasse::swap
> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container, die in der C++-Standardbibliothek verwendet werden, aufgeführt. Weitere Informationen finden Sie unter [C++ Standard Library Containers (C++-Standardbibliothekcontainer)](../standard-library/stl-containers.md).  
  
Tauscht die gesteuerten Sequenzen zwischen **\*this** und seinem Argument aus  
  
## <a name="syntax"></a>Syntax  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>Hinweise  
Wenn **\*this.get\_allocator ==** _right_**.get_allocator** gilt, erfolgt eine Austausch in konstanter Zeit. Andernfalls führt Sie proportional zur Anzahl der Elemente in den beiden kontrollierten Sequenzen eine Reihe von Elementzuweisungen und Konstruktoraufrufe aus.  
  
## <a name="see-also"></a>Siehe auch  
[Sample Container Class (Beispielcontainerklasse)](../standard-library/sample-container-class.md)

