---
title: Comptr::&amp; Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0afff1699a4c7a3a14f07967cfb5ba5727ba0320
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461561"
---
# <a name="comptroperatoramp-operator"></a>Comptr::&amp; Operator
Gibt die Schnittstelle frei zugeordneten **ComPtr** -Objekt und ruft dann die Adresse des der **ComPtr** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Einen schwachen Verweis auf das aktuelle **ComPtr**.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode unterscheidet sich von [comptr:: Getaddressof](../windows/comptr-getaddressof-method.md) , gibt diese Methode einen Verweis auf den Schnittstellenzeiger auf. Verwendung `ComPtr::GetAddressOf` Wenn muss die Adresse des Schnittstellenzeigers, jedoch nicht diese Schnittstelle freigeben möchten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)