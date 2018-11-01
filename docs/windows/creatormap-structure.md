---
title: CreatorMap-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a7bf4ec2132e19989c5f1ae7c47003056928d0fd
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234934"
---
# <a name="creatormap-structure"></a>CreatorMap-Struktur

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Hinweise

Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.

`CreatorMap` enthält folgende Informationen:

- So initialisieren, registrieren und Aufheben der Registrierung Objekten.

- Wie Aktivierungsdaten abhängig von einer klassischen COM- oder Windows-Runtime-Factory verglichen.

- Informationen zu den Factory Cache und Server-Namen für eine Schnittstelle.

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

Name                                          | Beschreibung
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[Creatormap:: ActivationID](#activationid)     | Stellt eine Objekt-ID, die durch eine klassische COM-Klassen-ID oder einen Namen für die Windows-Runtime identifiziert wird.
[Creatormap:: Factorycache](#factorycache)     | Speichert den Zeiger auf den Cache Factory für die `CreatorMap`.
[Creatormap:: FactoryCreator](#factorycreator) | Erstellt eine Factory für den angegebenen `CreatorMap`.
[Creatormap:: Servername](#servername)         | Speichert den Servernamen für die `CreatorMap`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CreatorMap`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="activationid"></a>Creatormap:: ActivationID

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Eine Schnittstellen-ID.

*getRuntimeName*<br/>
Eine Funktion, die den Windows-Runtime-Namen eines Objekts abruft.

### <a name="remarks"></a>Hinweise

Stellt eine Objekt-ID, die durch eine klassische COM-Klassen-ID oder Name einer Windows-Runtime identifiziert wird.

## <a name="factorycache"></a>Creatormap:: Factorycache

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Hinweise

Speichert den Zeiger auf den Cache Factory für die `CreatorMap`.

## <a name="factorycreator"></a>Creatormap:: FactoryCreator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Parameter

*currentflags*<br/>
Eines der [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.

*entry*<br/>
Eine CreatorMap.

*iidClassFactory*<br/>
Die Schnittstellen-ID von einer Klassenfactory.

*Factory*<br/>
Wenn der Vorgang abgeschlossen ist, die Adresse einer Klassenfactory.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Erstellt eine Factory für die angegebene CreatorMap an.

## <a name="servername"></a>Creatormap:: Servername

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Hinweise

Speichert den Servernamen für die CreatorMap an.
