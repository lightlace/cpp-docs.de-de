---
title: IID_PPV_ARGS_Helper-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0cef979ae284a303b120df7d14ae71f311498423
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882341"
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