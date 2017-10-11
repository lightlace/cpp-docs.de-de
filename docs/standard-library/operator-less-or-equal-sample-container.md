---
title: operator&lt;= (&lt;Sample Container&gt;) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
dev_langs:
- C++
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 43a0e51a226340965d24b0e2979c440b97b5fefe
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;= (&lt;Sample Container&gt;)
> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekscontainer](../standard-library/stl-containers.md).  
  
 Überlädt **operator<=**, um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
bool operator<=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `!(right < left)`zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\<sample container>](../standard-library/sample-container.md)


