---
title: ActivationFactoryCallback-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e2e7b2301ae4dd38a40bdf4583e963e55a8b12d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461392"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback-Funktion
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *activationId*  
 Handle für eine Zeichenfolge, die einen Common Language Runtime-Klassennamen angibt.  
  
 *ppFactory*  
 Wenn dieser Vorgang abgeschlossen ist, eine aktivierungsfactory, der Parameter entspricht *ActivationId*.  
  
## <a name="return-value"></a>Rückgabewert  
 „S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Wahrscheinlich Fehler-HRESULTs sind CLASS_E_CLASSNOTAVAILABLE und E_INVALIDARG zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Ruft die aktivierungsfactory für die Aktivierung der angegebenen ID.  
  
 Die Windows-Runtime ruft diese Callback-Funktion, um ein Objekt, das durch den Namen der Common Language Runtime-Klasse angegebenen anzufordern.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)