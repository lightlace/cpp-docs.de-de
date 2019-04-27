---
title: CAtlFileMapping-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: d0a47a6cf0cc86409ceb9ef40d6fc6d738c86aa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247170"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping-Klasse

Diese Klasse stellt eine Speicherabbilddatei, die Methoden der Cast-Operator hinzugefügt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten, die für die Cast-Operator verwendet werden soll.

## <a name="members"></a>Member

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlFileMapping::operator T *](#operator_t_star)|Ermöglicht die implizite Konvertierung von `CAtlFileMapping` Objekte `T*`.|

## <a name="remarks"></a>Hinweise

Diese Klasse fügt einen einzelne Cast-Operator, um ermöglichen die implizite Konvertierung des `CAtlFileMapping` Objekte `T*`. Andere Mitglieder werden bereitgestellt, von der Basisklasse, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Anforderungen

**Header:** atlfile.h

##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *

Ermöglicht die implizite Konvertierung von `CAtlFileMapping` Objekte `T*`.

```
operator T*() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine `T*` Zeiger am Anfang der Datei mit zugewiesenem Speicher.

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) und interpretiert die zurückgegebenen Zeiger als einen `T*` , in denen *T* ist der Typ als den Vorlagenparameter dieser Klasse verwendet.

## <a name="see-also"></a>Siehe auch

[CAtlFileMappingBase-Klasse](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
