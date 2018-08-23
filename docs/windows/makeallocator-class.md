---
title: MakeAllocator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e27be8eaddfc22474f15d7f9358050273252bf8a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610323"
---
# <a name="makeallocator-class"></a>MakeAllocator-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<
   typename T,
   bool hasWeakReferenceSupport =
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>Parameter

*T*  
Ein Typname.

*hasWeakReferenceSupport*  
**"true"** zum Zuweisen von Arbeitsspeicher für ein Objekt, das schwache Verweise; unterstützt. **"false"** zum Zuweisen von Arbeitsspeicher für ein Objekt, das schwache Verweise nicht unterstützt.

## <a name="remarks"></a>Hinweise

Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung von schwachen Verweis.

Überschreiben der **MakeAllocator** Klasse, um eine benutzerdefinierte Zuordnung Speichermodell zu implementieren.

**MakeAllocator** wird normalerweise verwendet, um Speicherverluste zu verhindern, wenn ein Objekt während der Erstellung auslöst.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[MakeAllocator::MakeAllocator-Konstruktor](../windows/makeallocator-makeallocator-constructor.md)|Initialisiert eine neue Instanz der dem **MakeAllocator** Klasse.|
|[MakeAllocator::~MakeAllocator-Destruktor](../windows/makeallocator-tilde-makeallocator-destructor.md)|Hebt die Initialisierung der aktuellen Instanz von der **MakeAllocator** Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[MakeAllocator::Allocate-Methode](../windows/makeallocator-allocate-method.md)|Weist Speicher zu und ordnet es die aktuellen **MakeAllocator** Objekt.|
|[MakeAllocator::Detach-Methode](../windows/makeallocator-detach-method.md)|Hebt die Zuordnung von belegten Arbeitsspeicher die [Allocate](../windows/makeallocator-allocate-method.md) Methode aus dem aktuellen **MakeAllocator** Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`MakeAllocator`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)