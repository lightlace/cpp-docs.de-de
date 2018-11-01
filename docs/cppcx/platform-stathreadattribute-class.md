---
title: 'Platform:: STAThreadAttribute-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb97be3012ae4a7c21765d33904f0914d7530025
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162047"
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute-Klasse

Legt Singlethreaded Apartment (STA) als Threadingmodell für Anwendungen fest.

## <a name="syntax"></a>Syntax

```
public ref class STAThreadAttribute sealed : Attribute
```

### <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[STAThreadAttribute-Konstruktor 1](#ctor)|Initialisiert eine neue Instanz der Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

Das STAThreadAttribute-Attribut erbt von [Platform:: Object Class](../cppcx/platform-object-class.md). „STAThreadAttribute“ wird zudem überladen oder weist die folgenden Member auf:

|name|Beschreibung|
|----------|-----------------|
|[STAThreadAttribute::Equals](#equals)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|
|[STAThreadAttribute::GetHashCode](#gethashcode)|Gibt den Hashcode für diese Instanz zurück.|
|[STAThreadAttribute::ToString](#tostring)|Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Platform`

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Platform

## <a name="ctor"></a> STAThreadAttribute constructor

Initialisiert eine neue Instanz der STAThreadAttribute-Klasse.

### <a name="syntax"></a>Syntax

```cpp
public:STAThreadAttribute();
```

## <a name="equals"></a> STAThreadAttribute::Equals

Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.

### <a name="syntax"></a>Syntax

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>Parameter

*obj*<br/>
Das zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Objekte gleich; andernfalls sind, **"false"**.

## <a name="gethashcode"></a> STAThreadAttribute::GetHashCode

Gibt den Hashcode für diese Instanz zurück.

### <a name="syntax"></a>Syntax

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Rückgabewert

Der Hashcode für diese Instanz.

## <a name="tostring"></a> STAThreadAttribute::ToString

Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.

### <a name="syntax"></a>Syntax

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die das aktuelle Objekt darstellt.

## <a name="see-also"></a>Siehe auch

[Plattform-Namespace](platform-namespace-c-cx.md)