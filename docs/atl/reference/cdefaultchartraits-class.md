---
title: CDefaultCharTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 8ea73da76f079359a4fc0250cacf70d10b545038
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660833"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits-Klasse

Diese Klasse stellt zwei statische Funktionen zum Konvertieren von Zeichen zwischen Groß- und Kleinbuchstaben.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDefaultCharTraits::CharToLower](#chartolower)|(Statisch) Mit dieser Funktion können Sie ein Zeichen in Großbuchstaben zu konvertieren.|
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Statisch) Rufen Sie diese Funktion, um ein Zeichen in Kleinbuchstaben zu konvertieren.|

## <a name="remarks"></a>Hinweise

Diese Klasse bietet Funktionen, die von der Klasse verwendet werden [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="chartolower"></a>  CDefaultCharTraits::CharToLower

Rufen Sie diese Funktion, um ein Zeichen in Kleinbuchstaben zu konvertieren.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Das Zeichen in Kleinbuchstaben konvertiert werden soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

##  <a name="chartoupper"></a>  CDefaultCharTraits::CharToUpper

Mit dieser Funktion können Sie ein Zeichen in Großbuchstaben zu konvertieren.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Das Zeichen, die in Großbuchstaben zu konvertieren.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
