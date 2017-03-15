---
title: Containerklasse::erase | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 0a28e1ff0def707926a67e1fea77f40e9927c0c4
ms.lasthandoff: 02/24/2017

---
# <a name="container-classerase"></a>Container-Klasse::erase
> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container, die in der C++-Standardbibliothek verwendet werden, aufgeführt. Weitere Informationen finden Sie unter [C++ Standard Library Containers (C++-Standardbibliothekcontainer)](../standard-library/stl-containers.md).  
  
 Löscht ein Element  
  
## <a name="syntax"></a>Syntax  
  
```  
 
    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,  
    iterator last);
```  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt das Element der gesteuerten Sequenz, auf das durch _*Where*** verwiesen wird.** Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich [` first`, ` last`). Beide Memberfunktionen geben einen Iterator zurück, der das erste Element festlegt, das länger als alle anderen entfernten Elementen verbleibt, oder sie geben [end](../standard-library/container-class-end.md) zurück, wenn kein solches Element vorhanden ist.  
  
 Die Memberfunktion löst nur dann eine Ausnahme aus, wenn ein Kopiervorgang eine Ausnahme auslöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Sample Container Class (Beispielcontainerklasse)](../standard-library/sample-container-class.md)

