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
ms.openlocfilehash: fa5988516f3836749357b15295ac228b78fe3f04
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467240"
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion-Methode
Ruft den Ereignishandler für den Abschluss, oder setzt den internen Status-Delegaten.  
  
## <a name="syntax"></a>Syntax  
  
```  
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