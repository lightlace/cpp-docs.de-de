---
title: RuntimeClass-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f6cca23834eb889ecb83d91b40861b92fe922ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605983"
---
# <a name="runtimeclass-class"></a>RuntimeClass-Klasse

Stellt eine WinRT oder COM-Klasse, die die angegebene Schnittstelle erbt und die angegebenen Windows-Runtime, Klassisches COM und schwachen Verweis-Unterstützung.

Diese Klasse stellt die Codebausteine-Implementierung von WinRT und COM-Klassen, die die Implementierung von `QueryInterface`, `AddRef`, `Release` usw. verwaltet den Verweiszähler des Moduls und verfügt über Unterstützung für die Bereitstellung der Klassenfactory für aktivierbare Objekte.

## <a name="syntax"></a>Syntax

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Parameter

*classFlags*  
Optionale Parameter. Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) -Enumerationswerte fest. Die `__WRL_CONFIGURATION_LEGACY__` Makro definiert werden kann, um den Standardwert ClassFlags für alle Common Language Runtime-Klassen im Projekt zu ändern. Wenn definiert, sind RuntimeClass-Instanzen standardmäßig nicht agile. Wenn Sie nicht definiert ist, sind RuntimeClass-Instanzen standardmäßig agile. Um zu vermeiden Mehrdeutigkeit Geben Sie immer die `Microsoft::WRL::FtmBase` in `TInterfaces` oder `RuntimeClassType::InhibitFtmBase`. Beachten Sie, wenn InhibitFtmBase und FtmBase sind, dass sowohl das Objekt verwendet, werden als agile.

*TInterfaces*  
Die Liste der Schnittstellen das Objekt implementiert, über `IUnknown`, `IInspectable` oder anderen Schnittstellen gesteuert durch [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Kann auch andere Klassen von, abgeleitet werden, insbesondere auflisten `Microsoft::WRL::FtmBase` agil machen, das Objekt, und dazu führen, dass implementieren `IMarshal`.

## <a name="members"></a>Member

`RuntimeClassInitialize` Eine Funktion, die das Objekt initialisiert, wenn die `MakeAndInitialize` Vorlagenfunktion zum Erstellen des Objekts verwendet wird. Es gibt S_OK zurück, wenn das Objekt erfolgreich initialisiert wurde, oder eine COM-Fehlercode zurück, wenn Fehler bei der Initialisierung. Die COM-Fehlercode als Rückgabewert der weitergegeben wird `MakeAndInitialize`. Beachten Sie, dass die `RuntimeClassInitialize` Methode wird nicht aufgerufen, wenn die `Make` Vorlagenfunktion zum Erstellen des Objekts verwendet wird.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[RuntimeClass::RuntimeClass-Konstruktor](../windows/runtimeclass-runtimeclass-constructor.md)|Initialisiert die aktuelle Instanz der RuntimeClass-Klasse.|
|[RuntimeClass::~RuntimeClass-Destruktor](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der RuntimeClass-Klasse auf.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

Dies ist ein Implementierungsdetail.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)