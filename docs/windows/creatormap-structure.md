---
title: CreatorMap-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0a622eaa40cedfd7bf22259cf81382290f20f3a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593733"
---
# <a name="creatormap-structure"></a>CreatorMap-Struktur

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Hinweise

Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.

**CreatorMap** enthält die folgenden Informationen:

- So initialisieren, registrieren und Aufheben der Registrierung Objekten.

- Wie Aktivierungsdaten abhängig von einer klassischen COM- oder Windows-Runtime-Factory verglichen.

- Informationen zu den Factory Cache und Server-Namen für eine Schnittstelle.

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CreatorMap::activationId-Datenmember](../windows/creatormap-activationid-data-member.md)|Stellt eine Objekt-ID, die durch eine klassische COM-Klassen-ID oder einen Namen für die Windows-Runtime identifiziert wird.|
|[CreatorMap::factoryCache-Datenmember](../windows/creatormap-factorycache-data-member.md)|Speichert den Zeiger auf den Cache Factory für die **CreatorMap**.|
|[CreatorMap::factoryCreator-Datenmember](../windows/creatormap-factorycreator-data-member.md)|Erstellt eine Factory für den angegebenen **CreatorMap**.|
|[CreatorMap::serverName-Datenmember](../windows/creatormap-servername-data-member.md)|Speichert den Servernamen für die **CreatorMap**.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CreatorMap`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)