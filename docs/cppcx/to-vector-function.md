---
title: To_vector-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c345b594c284c1273a080d979cd9588aff350d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087970"
---
# <a name="tovector-function"></a>to_vector-Funktion
Gibt `std::vector` zurück, dessen Wert der Auflistung entspricht, die dem angegebenen IVector- oder IVectorView-Parameter zugrunde liegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename T>  
inline ::std::vector<T> to_vector(IVector<T>^ v); 
 
template <typename T>  
inline ::std::vector<T> to_vector(IVectorView<T>^ v);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Vorlagentyp-Parameter.  
  
 `v`  
 Eine IVector- oder IVectorView-Schnittstelle, die Zugriff auf ein zugrunde liegendes Vektor- oder VectorView-Objekt bietet.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>Siehe auch  
 [Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)