---
title: 'Comptr:: Comptr-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05440f9d6a7f243432dfa118cf1e137d9c5428d2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429317"
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr-Konstruktor

Initialisiert eine neue Instanz der dem **ComPtr** Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW ComPtr();
WRL_NOTHROW ComPtr(
   decltype(__nullptr)  
);
template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr(
   const ComPtr& other
);
template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
```

### <a name="parameters"></a>Parameter

*U*<br/>
Der Typ des der *andere* Parameter.

*other*<br/>
Ein Objekt des Typs *U*.

## <a name="return-value"></a>Rückgabewert

## <a name="remarks"></a>Hinweise

Der erste Konstruktor ist der Standardkonstruktor, der implizit ein leeres Objekt erstellt. Gibt an, der zweite Konstruktor [__nullptr](../windows/nullptr-cpp-component-extensions.md), die explizit erstellt ein leeres Objekt.

Der dritte Konstruktor erstellt ein Objekt aus dem Objekt, das durch einen Zeiger angegeben.

Die vierten und fünften Konstruktoren sind Kopierkonstruktoren Der fünfte Konstruktor kopiert ein Objekt aus, wenn es auf den aktuellen Typ konvertiert werden kann.

Die sechsten und siebten Konstruktoren sind Move-Konstruktoren. Der siebte Konstruktor verschiebt ein Objekt aus, wenn es auf den aktuellen Typ konvertiert werden kann.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)