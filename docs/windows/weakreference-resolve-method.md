---
title: 'WeakReference:: Resolve-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs: C++
helpviewer_keywords: Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4da4689ffd8fa0a633b3f481b0292d060e57345
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Eine Schnittstellen-ID.  
  
 `ppvObject`  
 Wenn dieser Vorgang abgeschlossen wird, eine Kopie der aktuellen starke Verweis, wenn die Anzahl der starken Verweis ungleich NULL ist.  
  
## <a name="return-value"></a>Rückgabewert  
  
-   S_OK, wenn dieser Vorgang erfolgreich ist und die Anzahl der starken Verweis ist NULL. Der `ppvObject`-Parameter ist auf `nullptr` festgelegt.  
  
-   S_OK, wenn dieser Vorgang erfolgreich ist und die Anzahl der starken Verweis ist ungleich NULL. Die `ppvObject` Parameter auf der starke Verweis festgelegt ist.  
  
-   Andernfalls failed ein HRESULT, das den Grund angibt, diesen Vorgang.  
  
## <a name="remarks"></a>Hinweise  
 Legt des angegebenen Zeigers auf den aktuellen Wert der starken Verweis, wenn die Anzahl der starken Verweis ungleich NULL ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [WeakReference Class1](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)