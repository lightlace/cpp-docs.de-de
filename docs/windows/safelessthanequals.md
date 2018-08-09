---
title: SafeLessThanEquals | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThanEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThanEquals function
ms.assetid: cbd70526-faf2-4fbc-96a0-b61e8cf5f04a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4297094a6664e695f79f1e0b02625b0b6964ca95
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016823"
---
# <a name="safelessthanequals"></a>SafeLessThanEquals
Vergleicht zwei Zahlen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <typename T, typename U>  
inline bool SafeLessThanEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *t*  
 Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.  
  
 [in] *u*  
 Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn *t* ist kleiner als oder gleich *u*andernfalls **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 **SafeLessThanEquals** erweitert den regulären Vergleichsoperator ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen verglichen werden soll.  
  
 Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ohne eine Instanz des für einen einzelnen Vergleich aus dient die [SafeInt-Klasse](../windows/safeint-class.md).  
  
> [!NOTE]
>  Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen.  
  
 Weitere Informationen zu den Vorlagentypen `T` und `U`, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Funktionen](../windows/safeint-functions.md)   
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeInt-Klasse](../windows/safeint-class.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThan](../windows/safelessthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)