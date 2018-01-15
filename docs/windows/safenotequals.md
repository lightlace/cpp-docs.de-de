---
title: SafeNotEquals | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeNotEquals
dev_langs: C++
helpviewer_keywords: SafeNotEquals function
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1d4449d66f82db73b39c7b3be3ce85ba92ab88d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="safenotequals"></a>SafeNotEquals
Bestimmt, ob zwei Zahlen ungleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeNotEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `t`  
 Die erste zu vergleichende Zahl. Dies muss vom Typ t sein.  
  
 [in] `u`  
 Die zweite zu vergleichende Zahl. Dies muss vom Typ u sein.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn `t` und `u` nicht gleich sind; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die Methode erweitert `!=` da `SafeNotEquals` ermöglicht Ihnen, zwei verschiedene Arten von Zahlen zu vergleichen.  
  
 Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und eignet sich für einen einzelnen Vergleich aus ohne Erstellen einer Instanz von der [SafeInt-Klasse](../windows/safeint-class.md).  
  
> [!NOTE]
>  Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen aufrufen.  
  
 Weitere Informationen zu den Vorlagentypen T "und" U, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Funktionen](../windows/safeint-functions.md)   
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeInt-Klasse](../windows/safeint-class.md)   
 [SafeEquals](../windows/safeequals.md)