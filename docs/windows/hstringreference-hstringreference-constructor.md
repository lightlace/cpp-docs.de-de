---
title: 'Hstringreference:: Hstringreference-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7dce8c6fca14ad26665bf4868681234374c20f85
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608143"
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference-Konstruktor
Initialisiert eine neue Instanz der dem **HStringReference** Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *sizeDest*  
 Ein Vorlagenparameter, der angibt, die Größe des Ziels **HStringReference** Puffer.  
  
 *str*  
 Ein Verweis auf eine Zeichenfolge mit Breitzeichen.  
  
 *Len*  
 Die maximale Länge von der *str* Parameterpuffer auf diesen Vorgang verwendet. Wenn die *Len* Parameter nicht angegeben ist, die gesamte *str* Parameter wird verwendet. Wenn *Len* ist größer als *SizeDest*, *Len* nastaven NA hodnotu *SizeDest*-1.  
  
 *other*  
 Eine andere **HStringReference** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert eine neue **HStringReference** -Objekt, das dieselbe, als Parameter Größe *str*.  
  
 Der zweite Konstruktor initialisiert eine neue **HStringReference** -Objekt, das Größe Specifeid durch Parameter *Len*.  
  
 Der dritte Konstruktor initialisiert eine neue **HStringReference** Objekt, das den Wert des der *andere* Parameter, und dann zerstört die *andere* Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)