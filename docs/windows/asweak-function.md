---
title: AsWeak-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75d732758bac53edc40aeac50e0184d80145890d
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="asweak-function"></a>AsWeak-Funktion
Ruft einen schwachen Verweis zur angegebenen Instanz ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein Zeiger auf den Typ des Parameters `p`.  
  
 `p`  
 Eine Instanz eines Typs.  
  
 `pWeak`  
 Wenn dieser Vorgang abgeschlossen wird, einen Zeiger auf einen schwachen Verweis auf Parameter `p`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das die Ursache des Fehlers angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)