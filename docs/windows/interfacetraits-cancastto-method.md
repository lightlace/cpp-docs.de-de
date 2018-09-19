---
title: 'Interfacetraits:: Cancastto-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aea326149c9748ff480d523a1078f54ba733cb14
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610419"
---
# <a name="interfacetraitscancastto-method"></a>InterfaceTraits::CanCastTo-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameter

*ptr*  
Der Name eines Zeigers auf einen Typ.

*riid*  
Die Schnittstellen-ID des `Base`.

*ppv*  
Wenn dieser Vorgang erfolgreich ist, ist *Ppv* verweist auf die angegebene Schnittstelle `Base`. Andernfalls *Ppv* nastaven NA hodnotu **"nullptr"**.

## <a name="return-value"></a>Rückgabewert

**"true"** , wenn dieser Vorgang erfolgreich ist und *Ptr* der Umwandlung in einen Zeiger auf `Base`ist, andernfalls **"false"** .

## <a name="remarks"></a>Hinweise

Gibt an, ob der angegebene Zeiger umgewandelt werden kann, auf einen Zeiger auf `Base`.

Weitere Informationen zu `Base`, finden Sie unter den **öffentliche Typedefs** im Abschnitt [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)