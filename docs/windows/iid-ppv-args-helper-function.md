---
title: IID_PPV_ARGS_Helper-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d1d2809111bbf33238319ca4fe462f7542bd6d1c
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper-Funktion
Stellt sicher, dass der Typ des angegebenen Arguments abgeleitet die `IUnknown` Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Spezialisierung einer Klassenvorlage unterstützt die WRL-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden. Verwendung [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Arguments `pp`.  
  
 `pp`  
 Ein doppelt indirekter Zeiger.  
  
## <a name="return-value"></a>Rückgabewert  
 Argument `pp` umgewandelt in einen Zeiger-auf-a-Zeiger auf `void`.  
  
## <a name="remarks"></a>Hinweise  
 Ein Fehler während der Kompilierung wird generiert, wenn die Vorlagenparameter `T` nicht ableiten `IUnknown`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz (Windows-Runtime-Bibliothek)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)