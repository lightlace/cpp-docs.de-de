---
title: CNotSupportedException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: c3af508cd39e277ca4ae0a9aad5e639f66edc53b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294810"
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException-Klasse

Stellt eine Ausnahme dar, die das Ergebnis der Anforderung einer nicht unterstützten Funktion ist.

## <a name="syntax"></a>Syntax

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Erstellt ein `CNotSupportedException`-Objekt.|

## <a name="remarks"></a>Hinweise

Keine weiteren Qualifizierung ist erforderlich oder möglich.

Weitere Informationen zur Verwendung von `CNotSupportedException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException

Erstellt ein `CNotSupportedException`-Objekt.

```
CNotSupportedException();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Weitere Informationen zur ausnahmeverarbeitung finden Sie im Artikel [Ausnahmebehandlung in MFC](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[CException-Klasse](cexception-class.md)<br/>
[Hierarchiediagramm](../hierarchy-chart.md)
