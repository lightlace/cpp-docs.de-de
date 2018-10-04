---
title: RuntimeClassBaseT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c46e89dc11f4c6fe216cfd61c3222a9c52d9e45
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789136"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parameter

*RuntimeClassTypeT*<br/>
Ein Feld von Flags, der angibt, eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.

## <a name="remarks"></a>Hinweise

Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.

## <a name="members"></a>Member

### <a name="protected-methods"></a>Geschützte Methoden

Name                                                         | Beschreibung
------------------------------------------------------------ | -----------------------------------------------------------------------------
[Runtimeclassbaset:: Asiid](#asiid)                           | Ruft einen Zeiger auf die angegebene Schnittstellen-ID.
[Runtimeclassbaset:: Getimplementediids](#getimplementediids) | Ruft ein Array von Schnittstellen-IDs, die von einem angegebenen Typ implementiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`RuntimeClassBaseT`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="asiid"></a>Runtimeclassbaset:: Asiid

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Typ, die Schnittstellen-ID, die vom Parameter angegebene implementiert *Riid*.

*Implementiert*<br/>
Eine Variable des Typs von Template-Parameter angegebenen *T*.

*riid*<br/>
Die Schnittstellen-ID abgerufen werden soll.

*ppvObject*<br/>
Wenn dieser Vorgang erfolgreich ist, wird ein Zeiger-auf-a-Zeiger auf die Schnittstelle vom-Parameter angegebenen *Riid*.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

### <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die angegebene Schnittstellen-ID.

## <a name="getimplementediids"></a>Runtimeclassbaset:: Getimplementediids

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des der *implementiert* Parameter.

*Implementiert*<br/>
Zeiger auf den vom Parameter angegebenen Typ *T*.

*iidCount*<br/>
Die maximale Anzahl von Schnittstellen-IDs abrufen.

*IIDs*<br/>
Wenn dieser Vorgang erfolgreich abgeschlossen, ein Array von die Schnittstellen-IDs, die vom Typ implementiert wird *T*.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

### <a name="remarks"></a>Hinweise

Ruft ein Array von Schnittstellen-IDs, die von einem angegebenen Typ implementiert werden.
