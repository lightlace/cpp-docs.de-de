---
title: 'Platform:: ValueType-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae1cab3d5cde3bc39f131acd1b01976dcb6d522b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105106"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType-Klasse

Die Basisklasse für Instanzen von Werttypen.

## <a name="syntax"></a>Syntax

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|[ValueType::ToString](#tostring)|Gibt eine Zeichenfolgendarstellung des Objekts zurück. Geerbt von [Platform:: Object](../cppcx/platform-object-class.md).|

### <a name="remarks"></a>Hinweise

Die ValueType-Klasse wird zum Erstellen von Werttypen verwendet. „ValueType“ ist von „Object“ abgeleitet, die über Basismember verfügt. Der Compiler trennt jedoch diese Basismember von den Werttypen, die aus der ValueType-Klasse abgeleitet sind. Der Compiler fügt die Basismember wieder an, wenn ein Werttyp mittels Boxing konvertiert wird.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="tostring"></a> ValueType:: ToString-Methode

Gibt eine Zeichenfolgendarstellung des Objekts zurück.

### <a name="syntax"></a>Syntax

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Rückgabewert

Ein Platform:: String-Wert, der den Wert darstellt.

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)