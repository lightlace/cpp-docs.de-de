---
title: 'Asyncbase:: Fireprogress-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c2c5aab609b597c3a9ff464b868ba831889deed
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863581"
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress-Methode
Wird der aktuelle Fortschritt-Ereignishandler aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `arg`  
 Die Ereignishandlermethode aufgerufen.  
  
## <a name="remarks"></a>Hinweise  
 `ProgressTraits` stammt aus [ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)