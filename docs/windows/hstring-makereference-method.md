---
title: 'Hstring:: Makereference-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 673d5b10706580303f179ee453495b581d96eda3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608334"
---
# <a name="hstringmakereference-method"></a>HString::MakeReference-Methode
Erstellt eine `HStringReference` Objekt aus einem angegebenen Zeichenfolgenparameter.  
  
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
  
### <a name="parameters"></a>Parameter  
 *sizeDest*  
 Ein Vorlagenparameter, der angibt, die Größe des Ziels `HStringReference` Puffer.  
  
 *str*  
 Ein Verweis auf eine Zeichenfolge mit Breitzeichen.  
  
 *Len*  
 Die maximale Länge von der *str* Parameterpuffer auf diesen Vorgang verwendet. Wenn die *Len* Parameter nicht angegeben ist, die gesamte *str* Parameter wird verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein `HStringReference` -Objekt, dessen Wert identisch mit dem angegebenen ist *str* Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)