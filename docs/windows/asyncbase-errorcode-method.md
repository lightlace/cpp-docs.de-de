---
title: 'Asyncbase:: ErrorCode-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abd3eae18d793739866b6c0dd8a1b6a994093c93
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859578"
---
# <a name="asyncbaseerrorcode-method"></a>AsyncBase::ErrorCode-Methode
Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `error`  
 Der Speicherort, in dem dieser Vorgang den aktuellen Fehlercode speichert.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Vorgang ist threadsicher.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)