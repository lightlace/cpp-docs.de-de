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
ms.openlocfilehash: 705b495e3f6d626a742fd1a63989c8cc658446a4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379662"
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

*ptr*<br/>
Der Name eines Zeigers auf einen Typ.

*riid*<br/>
Die Schnittstellen-ID des `Base`.

*ppv*<br/>
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

[InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)