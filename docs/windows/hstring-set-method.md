---
title: 'Hstring:: Set-Methode | Microsoft Docs'
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
ms.openlocfilehash: 39c227e19cdadae80f32c25515a10dd0810f5726
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882416"
---
# <a name="hstringset-method"></a>HString::Set-Methode
Legt den Wert des aktuellen HString-Objekts auf die angegebene Zeichenfolge mit Breitzeichen oder den angegebenen HString-Parameter fest.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Eine Zeichenfolge mit Breitzeichen.  
  
 `len`  
 Die maximale Länge von der `str` Parameter, der mit dem aktuellen HString-Objekt zugewiesen ist.  
  
 `hstr`  
 Ein vorhandenes HString-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)