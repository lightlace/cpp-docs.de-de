---
title: Concurrency::Graphics::Direct3D-Namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d
- amp_short_vectors/Concurrency::graphics::direct3d
dev_langs:
- C++
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01d029b528280a89b2bc60639b47a23c5df6ffbc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405231"
---
# <a name="concurrencygraphicsdirect3d-namespace"></a>Concurrency::graphics::direct3d-Namespace

Stellt die [Get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture) und [Make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture) Methoden.

## <a name="syntax"></a>Syntax

```
namespace direct3d;
```

## <a name="members"></a>Member

### <a name="functions"></a>Funktionen

|Name<br /><br /> Beschreibung|
|--------------------------|
|[get_sampler](concurrency-graphics-direct3d-namespace-functions.md#get_sampler)<br /><br /> Rufen Sie die Direct3D-Samplerstatus-Schnittstelle für die angegebene Zugriffstastenansicht ab, die das angegebene Samplerobjekt darstellt.|
|[get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)<br /><br /> Ruft die zugrunde liegende angegebenen Direct3D-texturschnittstelle [Textur](texture-class.md) Objekt.|
|[make_sampler](concurrency-graphics-direct3d-namespace-functions.md#make_sampler)<br /><br /> Erstellen Sie einen Sampler aus einem Direct3D-Samplerstatusschnittstellenzeiger.|
|[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)<br /><br /> Erstellt eine [Textur](texture-class.md) Objekt mit den angegebenen Parametern.|
|[msad4](concurrency-graphics-direct3d-namespace-functions.md#msad4)<br /><br /> Vergleicht einen 4-Byte-Verweiswert und einen 8-Byte-Quellwert und sammelt einen Vektor von 4 Summen.|

## <a name="requirements"></a>Anforderungen

**Header:** amp_graphics.h

**Namespace:** Concurrency:: Graphics

## <a name="see-also"></a>Siehe auch

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
