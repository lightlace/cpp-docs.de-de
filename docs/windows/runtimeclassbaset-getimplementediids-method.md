---
title: 'Runtimeclassbaset:: Getimplementediids-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs: C++
helpviewer_keywords: GetImplementedIIDS method
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25410ac57e1812d3f4648151afff4f97d413689b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>RuntimeClassBaseT::GetImplementedIIDS-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des `implements`-Parameters.  
  
 `implements`  
 Zeiger auf den vom Parameter angegebenen Typ `T`.  
  
 `iidCount`  
 Die maximale Anzahl von Schnittstellen-IDs abzurufen.  
  
 `iids`  
 Wenn dieser Vorgang erfolgreich abgeschlossen, ein Array von Schnittstellen-IDs, die vom Typ implementiert wird `T`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Ruft ein Array von Schnittstellen-IDs, die von einem angegebenen Typ implementiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [RuntimeClassBaseT-Struktur](../windows/runtimeclassbaset-structure.md)