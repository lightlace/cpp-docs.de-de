---
title: 'Implementshelper:: Casttounknown-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66e45448d25cff013ad4a0d98e8cca403589581b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="implementshelpercasttounknown-method"></a>ImplementsHelper::CastToUnknown-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die zugrunde liegende IUnknown-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Ruft einen Zeiger auf die zugrunde liegenden IUnknown-Schnittstelle für die aktuelle Implements-Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ImplementsHelper-Struktur](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)