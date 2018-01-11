---
title: SafeMultiply | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeMultiply
dev_langs: C++
helpviewer_keywords: SafeMultiply function
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37ea091136521fc83fc63a8fb752e0f4f72cb49f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="safemultiply"></a>SafeMultiply
Multipliziert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf zusammen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `t`  
 Die erste zu multiplizierende Zahl. Dies muss vom Typ t sein.  
  
 [in] `u`  
 Die zweite zu multiplizierende Zahl. Dies muss vom Typ u sein.  
  
 [out] `result`  
 Der Parameter, in denen `SafeMultiply` speichert das Ergebnis.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn kein Fehler auftritt. `false` , wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und eignet sich für einen einzelnen Multiplikationsvorgang ohne Erstellen einer Instanz von der [SafeInt-Klasse](../windows/safeint-class.md).  
  
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
 [SafeDivide](../windows/safedivide.md)