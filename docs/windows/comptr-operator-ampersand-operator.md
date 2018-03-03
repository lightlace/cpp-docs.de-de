---
title: Comptr::&amp; Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc5234f10a16141fd91193d634f0d306886aff71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperatoramp-operator"></a>Comptr::&amp; Operator
Gibt die Schnittstelle frei zugeordnete `ComPtr` -Objekt und ruft dann die Adresse der `ComPtr` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Einen schwachen Verweis auf das aktuelle `ComPtr`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode unterscheidet sich von [comptr:: Getaddressof](../windows/comptr-getaddressof-method.md) , da diese Methode einen Verweis auf den Schnittstellenzeiger frei. Verwendung `ComPtr::GetAddressOf` Wenn Sie muss die Adresse des Schnittstellenzeigers, jedoch nicht diese Schnittstelle freigeben möchten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)