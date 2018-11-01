---
title: CResourceException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: aa7fd6e2caa15a256cec2eae5ede6c6e47cd1518
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632685"
---
# <a name="cresourceexception-class"></a>CResourceException-Klasse

Wird generiert, wenn Windows eine angeforderte Ressource nicht finden oder zuordnen kann.

## <a name="syntax"></a>Syntax

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|Erstellt ein `CResourceException`-Objekt.|

## <a name="remarks"></a>Hinweise

Keine weiteren Qualifizierung ist erforderlich oder möglich.

Weitere Informationen zur Verwendung von `CResourceException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cresourceexception"></a>  CResourceException::CResourceException

Erstellt ein `CResourceException`-Objekt.

```
CResourceException();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmebehandlung in MFC](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[CException-Klasse](cexception-class.md)<br/>
[Hierarchiediagramm](../hierarchy-chart.md)

