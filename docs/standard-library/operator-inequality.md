---
title: operator!= | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- std::!=
- '!='
- std::operator!=
- std.operator!=
- std.!=
- operator!=
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- operator!=
- operator !=
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cff517cc1a8231684ac3fd6d07cc6d6b2c68ebf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="operator"></a>Operator!=
> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).  
  
 Überlädt `operator!=`, um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
bool operator!=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `!(left == right)`zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\<sample container>](../standard-library/sample-container.md)

