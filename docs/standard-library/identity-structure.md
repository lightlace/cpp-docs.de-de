---
title: identity Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- utility/std::identity
- identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a7404d2c1a785fd66489421fd7b9689260e0986d
ms.lasthandoff: 02/24/2017

---
# <a name="identity-structure"></a>identity-Struktur
Eine Struktur, die eine Typdefinition als den Vorlagenparameter bereitstellt.  
  
## <a name="syntax"></a>Syntax  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Der zu identifizierende Wert.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse enthält die öffentliche Typdefinition `type`, was dem Vorlagenparametertyp entspricht. Es wird in Verbindung mit der Vorlagenfunktion [forward](../standard-library/utility-functions.md#forward) verwendet, um sicherzustellen, dass ein Funktionsparameter den gewünschten Typ aufweist.  
  
 Aufgrund der Kompatibilität mit älteren Codes definiert die Klasse auch die identity-Funktion `operator()`, welche deren Argument `left` zurückgibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<utility>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<utility>](../standard-library/utility.md)




