---
title: 'Asyncbase:: Fireprogress-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs: C++
helpviewer_keywords: FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dd7aa1d66697058d711edd38b3c2eb0679b73c07
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 `ProgressTraits`stammt aus [ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)