---
title: 'Comptr:: Swap-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::Swap
dev_langs: C++
helpviewer_keywords: Swap method
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a8ff215bf3461fcbcadd20b0680829af81630aa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comptrswap-method"></a>ComPtr::Swap-Methode
Tauscht die Schnittstelle, die von dem aktuellen ComPtr-Objekt verwaltet wird, gegen der Schnittstelle, die vom angegebenen ComPtr-Objekt verwaltet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void Swap(  
   _Inout_ ComPtr&& r  
);  
  
void Swap(  
   _Inout_ ComPtr& r  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `r`  
 Comptr-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)