---
title: 'ClassFactory:: Release-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ClassFactory::Release
dev_langs: C++
helpviewer_keywords: Release method
ms.assetid: 49da2002-f9d6-4d7f-8a65-48c20b1bf99f
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b53ba7e09e372bb7639c70cc2ee56a0e6a489f4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="classfactoryrelease-method"></a>ClassFactory::Release-Methode
Dekrementiert den Verweiszähler für das aktuelle ClassFactory-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 „S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ClassFactory-Klasse](../windows/classfactory-class.md)