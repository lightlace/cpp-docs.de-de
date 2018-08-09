---
title: 'Asyncbase:: Firecompletion-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs:
- C++
helpviewer_keywords:
- FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 199d84afe198c4fc41808144105ea704822aa00a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646606"
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion-Methode
Ruft den Ereignishandler für den Abschluss, oder setzt den internen Status-Delegaten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die erste Version des **FireCompletion()** der Delegatvariablen internen Status zurückgesetzt. Die zweite Version wird der Abschluss-Ereignishandler aufgerufen, wenn der asynchrone Vorgang abgeschlossen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)