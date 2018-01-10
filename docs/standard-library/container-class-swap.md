---
title: Containerklasse::swap | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09229429c64e895a722d52d203f0259cf69e6d24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="container-classswap"></a>Container-Klasse::swap
> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).  
  
Tauscht die gesteuerten Sequenzen zwischen **\*this** und seinem Argument aus  
  
## <a name="syntax"></a>Syntax  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>Hinweise  
Wenn **\*this.get\_allocator ==** _right_**.get_allocator** gilt, erfolgt eine Austausch in konstanter Zeit. Andernfalls führt Sie proportional zur Anzahl der Elemente in den beiden kontrollierten Sequenzen eine Reihe von Elementzuweisungen und Konstruktoraufrufe aus.  
  
## <a name="see-also"></a>Siehe auch  
[Sample Container Class (Beispielcontainerklasse)](../standard-library/sample-container-class.md)
