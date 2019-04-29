---
title: CreatorMap-Struktur
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 44d06f317661059bea92d8c6f27955606a964bb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398614"
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
[CreatorMap::activationId](#activationid)     | Stellt eine Objekt-ID, die durch eine klassische COM-Klassen-ID oder einen Namen für die Windows-Runtime identifiziert wird.
[CreatorMap::factoryCache](#factorycache)     | Speichert den Zeiger auf den Cache Factory für die `CreatorMap`.
[CreatorMap::factoryCreator](#factorycreator) | Erstellt eine Factory für den angegebenen `CreatorMap`.
[CreatorMap::serverName](#servername)         | Speichert den Servernamen für die `CreatorMap`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CreatorMap`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="activationid"></a>CreatorMap::activationId

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

## <a name="factorycache"></a>CreatorMap::factoryCache

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Hinweise

Speichert den Zeiger auf den Cache Factory für die `CreatorMap`.

## <a name="factorycreator"></a>CreatorMap::factoryCreator

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
Eines der [RuntimeClassType](runtimeclasstype-enumeration.md) Enumeratoren.

*entry*<br/>
Eine CreatorMap.

*iidClassFactory*<br/>
Die Schnittstellen-ID von einer Klassenfactory.

*factory*<br/>
Wenn der Vorgang abgeschlossen ist, die Adresse einer Klassenfactory.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Erstellt eine Factory für die angegebene CreatorMap an.

## <a name="servername"></a>CreatorMap::serverName

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Hinweise

Speichert den Servernamen für die CreatorMap an.
