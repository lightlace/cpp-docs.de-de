---
title: FactoryCache-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d56779b5df33f75c9147d34b55f8c2fc65204a82
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234540"
---
# <a name="factorycache-structure"></a>FactoryCache-Struktur

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Hinweise

Enthält den Speicherort, der eine Klassenfactory und ein Wert, der einen registrierten wrt-identifiziert oder COM-Klassenobjekt.

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

Name                              | Beschreibung
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[Factorycache:: Cookie](#cookie)   | Enthält einen Wert an, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert, und wird später beim Aufheben der Registrierung des Objekts verwendet.
[Factorycache:: Factory](#factory) | Verweist auf eine Windows-Runtime oder COM-Klassenfactory.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`FactoryCache`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="cookie"></a>Factorycache:: Cookie

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Hinweise

Enthält einen Wert an, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert, und wird später beim Aufheben der Registrierung des Objekts verwendet.

## <a name="factory"></a>Factorycache:: Factory

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Hinweise

Verweist auf eine Windows-Runtime oder COM-Klassenfactory.
