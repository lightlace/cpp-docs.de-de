---
title: Concurrency::direct3d-Namespace
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
ms.openlocfilehash: e1374acbd7061afaba372100cf6e69d9d717da8a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127032"
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d-Namespace

Der `direct3d`-Namespace enthält Funktionen, welche die D3D-Interoperabilität unterstützen. Sie ermöglicht die Verwendung von D3D-Ressourcen für Compute in amp-Code. Außerdem ermöglicht es die Verwendung von Ressourcen, die in amp in D3D-Code erstellt wurden, ohne dass redundante zwischen Kopien erstellt werden. Mithilfe C++ von amp können Sie die rechenintensiven Abschnitte Ihrer DirectX-Anwendungen inkrementell beschleunigen und die D3D-API für Daten verwenden, die aus amp-Berechnungen erstellt werden.

## <a name="syntax"></a>Syntax

```cpp
namespace direct3d;
```

## <a name="members"></a>Members

### <a name="classes"></a>Klassen

|Name|BESCHREIBUNG|
|----------|-----------------|
|[scoped_d3d_access_lock-Klasse](scoped-d3d-access-lock-class.md)|Ein RAII-Wrapper für eine D3D-Zugriffssperre auf einem `accelerator_view`-Objekt.|

### <a name="structures"></a>Strukturen

|Name|BESCHREIBUNG|
|----------|-----------------|
|[adopt_d3d_access_lock_t-Struktur](adopt-d3d-access-lock-t-structure.md)|Der Tagtyp, mit dem angegeben wird, dass die D3D-Zugriffssperre eher übernommen als abgerufen werden sollte.|

### <a name="functions"></a>Functions

|Name|BESCHREIBUNG|
|----------|-----------------|
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Gibt den absoluten Wert des Arguments zurück.|
|[gekl](concurrency-direct3d-namespace-functions-amp.md#clamp)|Ist überladen. Bindet _X an den angegebenen _Min- und _Max-Bereich|
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Zählt die Anzahl der festgelegten Bits in _X|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Erstellt eine [accelerator_view Klasse](accelerator-view-class.md) von einem Zeiger auf eine Direct3D-Geräteschnittstelle|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Erhält eine Sperre für eine accelerator_view, um D3D-Vorgänge für Ressourcen, die mit dem accelerator_view gemeinsam verwendet werden, sicher auszuführen|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Versuch, ohne Blockierung die D3D-Zugriffssperre für eine accelerator_view abzurufen.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Gibt die D3D-Zugriffssperre für die angegebene accelerator_view frei.|
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Ruft den Speicherort des ersten festgelegten Bits in _X ab und arbeitet dabei vom höchsten Bit in der Reihenfolge nach unten.|
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Ruft den Speicherort des ersten festgelegten Bits in _X ab und arbeitet dabei vom niedrigsten Bit in der Reihenfolge nach oben.|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Ruft die Schnittstelle des D3D-Puffers ab, die einem Array zugrunde liegt.|
|[IMAX](concurrency-direct3d-namespace-functions-amp.md#imax)|Vergleicht zwei Werte und gibt den Wert zurück, der größer ist.|
|[Imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Vergleicht zwei Werte und gibt den kleineren Wert zurück.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Gibt ein boolesches Flag zurück, das angibt, ob Timeout für die angegebene "accelerator_view" deaktiviert ist.|
|[geworden](concurrency-direct3d-namespace-functions-amp.md#mad)|Ist überladen. Führt eine arithmetische Multiplikation/Add-Operation für drei Argumente aus: _x \* _Y + _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Erstellt ein Array aus dem Schnittstellenzeiger eines D3D-Puffers.|
|[klein](concurrency-direct3d-namespace-functions-amp.md#noise)|Generiert mithilfe des Perlin-Noise-Algorithmus einen Zufallswert|
|[Bogenmaß](concurrency-direct3d-namespace-functions-amp.md#radians)|Konvertiert _X von Grad in Bogenmaß|
|[RCP](concurrency-direct3d-namespace-functions-amp.md#rcp)|Berechnet einen schnellen, ungefähren Kehrwert des Arguments|
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Kehrt die Reihenfolge der Bits in _X um|
|[auslasten](concurrency-direct3d-namespace-functions-amp.md#saturate)|Bindet _X im Bereich zwischen 0 und 1|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Ist überladen. Gibt das Vorzeichen des Arguments zurück|
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Gibt eine glatte Hermite-Interpolation zwischen 0 und 1 zurück, wenn _X im Bereich [_Min, _Max] liegt.|
|[Schritt](concurrency-direct3d-namespace-functions-amp.md#step)|Vergleicht zwei Werte und gibt, je nachdem welcher Wert größer ist, 0 oder 1 zurück|
|[Umax](concurrency-direct3d-namespace-functions-amp.md#umax)|Vergleicht zwei nicht signierte Werte und gibt den Wert zurück, der größer ist.|
|[-in](concurrency-direct3d-namespace-functions-amp.md#umin)|Vergleicht zwei nicht signierte Werte und gibt den kleineren Wert zurück.|

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp.h

**Namespace:** Parallelität

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
