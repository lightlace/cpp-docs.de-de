---
title: CD2DBrushProperties-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6268a4478fa361b521ac662852e62dd50c56621
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071809"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties-Klasse

Ein Wrapper für `D2D1_BRUSH_PROPERTIES`.

## <a name="syntax"></a>Syntax

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Überladen. Erstellt eine `CD2D_BRUSH_PROPERTIES` Struktur|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrushProperties::CommonInit](#commoninit)|Initialisiert das Objekt|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties

Erstellt eine CD2D_BRUSH_PROPERTIES-Struktur

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>Parameter

*_opacity*<br/>
Die Basis Durchlässigkeit des Pinsels. Der Standardwert ist 1,0.

*_transform*<br/>
Die Transformation, auf den Pinsel angewendet.

##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit

Initialisiert das Objekt

```
void CommonInit();
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
