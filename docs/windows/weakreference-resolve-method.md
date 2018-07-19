---
title: 'WeakReference:: Resolve-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dccdf7554f8d102230bedc18231feb74625d621b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890472"
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