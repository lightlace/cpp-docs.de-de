---
title: 'Hstring:: Set-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aecdafe81dcebc7867d30c46be1fee271e60154c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606396"
---
# <a name="hstringset-method"></a>HString::Set-Methode
Legt den Wert des aktuellen **HString** Objekt, das die angegebene Zeichenfolge mit Breitzeichen oder **HString** Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *str*  
 Eine Zeichenfolge mit Breitzeichen.  
  
 *Len*  
 Die maximale Länge von der *str* Parameter, der mit dem aktuellen zugewiesen ist **HString** Objekt.  
  
 *HSTR*  
 Eine vorhandene **HString** Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)