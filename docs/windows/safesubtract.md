---
title: SafeSubtract | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeSubtract
dev_langs: C++
helpviewer_keywords: SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 98114ebc7baee41970177e9c390f65fa5521544a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="safesubtract"></a>SafeSubtract
Subtrahiert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf an.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `t`  
 Die erste Zahl in der Subtraktion. Dies muss vom Typ t sein.  
  
 [in] `u`  
 Die zu subtrahierende Zahl `t`. Dies muss vom Typ u sein.  
  
 [out] `result`  
 Der Parameter, in denen `SafeSubtract` speichert das Ergebnis.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn kein Fehler auftritt. `false` , wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ohne Erstellen einer Instanz von für eine einzelnes Subtraktion dient der [SafeInt-Klasse](../windows/safeint-class.md).  
  
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
 [SafeAdd](../windows/safeadd.md)