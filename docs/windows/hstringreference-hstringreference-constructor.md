---
title: 'Hstringreference:: Hstringreference-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs: C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 398ea9403f784c30f8e015101c25b071f1d6fb29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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