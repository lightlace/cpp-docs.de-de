---
title: 'Hstringreference:: Hstringreference-Konstruktor | Microsoft Docs'
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
ms.openlocfilehash: dc88ea32d4384b36559a4a10da0a5975345bf0d7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference-Konstruktor
Initialisiert eine neue Instanz der HStringReference-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `sizeDest`  
 Ein Vorlagenparameter, der die Größe des Zielpuffers HStringReference angibt.  
  
 `str`  
 Ein Verweis auf eine Zeichenfolge mit Breitzeichen.  
  
 `len`  
 Die maximale Länge von der `str` Parameterpuffer bei diesem Vorgang verwenden. Wenn die `len` Parameter nicht angegeben ist, die gesamte `str` Parameter wird verwendet. Wenn `len` ist größer als `sizeDest`, `len` festgelegt ist, um `sizeDest`-1.  
  
 `other`  
 Ein weiteres HStringReference-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert ein neues HStringReference-Objekt, das dieselbe, als Parameter Größe `str`.  
  
 Der zweite Konstruktor initialisiert eine neue HStringReference-Objekt, das die Größe Specifeid durch Parameter `len`.  
  
 Der dritte Konstruktor initialisiert ein neues HStringReference-Objekt, auf den Wert, der die `other` Parameter, und anschließend zerstört die `other` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)