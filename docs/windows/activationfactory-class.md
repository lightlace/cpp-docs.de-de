---
title: ActivationFactory-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6775e9466ed337a070b6a234a4d65bb949a009e4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857954"
---
# <a name="activationfactory-class"></a>ActivationFactory-Klasse
Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `I0`  
 Die nullte-Schnittstelle.  
  
 `I1`  
 Die erste Schnittstelle.  
  
 `I2`  
 Die zweite Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 ActivationFactory bietet Registrierungsmethoden und grundlegende Funktionalität für die IActivationFactory-Schnittstelle. ActivationFactory ermöglicht Ihnen, eine benutzerdefinierte Factory-Implementierung zu senden.  
  
 Das folgende Codefragment veranschaulicht symbolisch ActivationFactory verwenden.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 Das folgende Codefragment zeigt, wie die [implementiert](../windows/implements-structure.md) Struktur mehr als drei Schnittstellen-IDs angeben.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ActivationFactory::ActivationFactory-Konstruktor](../windows/activationfactory-activationfactory-constructor.md)|Initialisiert die ActivationFactory-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ActivationFactory::AddRef-Methode](../windows/activationfactory-addref-method.md)|Inkrementiert den Verweiszähler des aktuellen ActivationFactory-Objekts.|  
|[ActivationFactory::GetIids-Methode](../windows/activationfactory-getiids-method.md)|Ruft ein Array von implementierten Schnittstellen-IDs ab.|  
|[ActivationFactory::GetRuntimeClassName-Methode](../windows/activationfactory-getruntimeclassname-method.md)|Ruft die Laufzeitklasse-Namen des Objekts, das den aktuellen ActivationFactory instanziiert.|  
|[ActivationFactory::GetTrustLevel-Methode](../windows/activationfactory-gettrustlevel-method.md)|Ruft die Vertrauensebene des Objekts, das den aktuellen ActivationFactory instanziiert.|  
|[ActivationFactory::QueryInterface-Methode](../windows/activationfactory-queryinterface-method.md)|Ruft einen Zeiger auf die angegebene Schnittstelle ab.|  
|[ActivationFactory::Release-Methode](../windows/activationfactory-release-method.md)|Dekrementiert den Verweiszähler des aktuellen ActivationFactory-Objekts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)