---
title: 'Hstring:: Makereference-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e2eba5756f2c18830c4c8fe7e16f2751ea61ac1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hstringmakereference-method"></a>HString::MakeReference-Methode
Erstellt ein HStringReference-Objekt aus einem angegebenen Zeichenfolgenparameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
#### <a name="parameters"></a>Parameter  
 `sizeDest`  
 Ein Vorlagenparameter, der die Größe des Zielpuffers HStringReference angibt.  
  
 `str`  
 Ein Verweis auf eine Zeichenfolge mit Breitzeichen.  
  
 `len`  
 Die maximale Länge von der `str` Parameterpuffer bei diesem Vorgang verwenden. Wenn die `len` Parameter nicht angegeben ist, die gesamte `str` Parameter wird verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein HStringReference-Objekt, dessen Wert identisch mit dem angegebenen ist `str` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)