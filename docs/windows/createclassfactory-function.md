---
title: CreateClassFactory-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95d08573515bee89fd86d6b37e3982dde2b29978
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870472"
---
# <a name="createclassfactory-function"></a>CreateClassFactory-Funktion
Erstellt eine Factory, die Instanzen der angegebenen Klasse erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `flags`  
 Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumerationswerte.  
  
 `entry`  
 Zeiger auf eine [CreatorMap](../windows/creatormap-structure.md) , Initialisierung und Registrierung Informationen über Parameter enthält `riid`.  
  
 `riid`  
 Verweis auf eine Schnittstellen-ID.  
  
 `ppFactory`  
 Wenn dieser Vorgang erfolgreich, einen Zeiger an eine Klassenfactory ausgeführt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Assert-Fehler wird ausgegeben, wenn Vorlagenparameter `Factory` nicht IClassFactory-Schnittstelle abgeleitet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)