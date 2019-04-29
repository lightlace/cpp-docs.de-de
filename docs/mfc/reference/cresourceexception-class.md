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
ms.openlocfilehash: b29112b4901a1fecac37aa7ae61496e874959370
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372193"
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
