---
title: 'Asyncbase:: OnCancel-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b648718c715a43befbc5ead828c810dbfa92d120
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646873"
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel-Methode
Ruft beim Überschreiben in einer abgeleiteten Klasse Bricht einen asynchronen Vorgang ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)   
 [AsyncBase::Cancel-Methode](../windows/asyncbase-cancel-method.md)