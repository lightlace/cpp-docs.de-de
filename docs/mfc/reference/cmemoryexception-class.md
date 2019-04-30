---
title: CMemoryException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 11be0eba080085c507ed718ea23219ca1c93aeba
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341181"
---
# <a name="cmemoryexception-class"></a>CMemoryException-Klasse

Stellt eine Ausnahmebedingung dar, die durch ungenügenden Arbeitsspeicher ausgelöst wird.

## <a name="syntax"></a>Syntax

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMemoryException::CMemoryException](#cmemoryexception)|Erstellt ein `CMemoryException`-Objekt.|

## <a name="remarks"></a>Hinweise

Keine weiteren Qualifizierung ist erforderlich oder möglich. Memory-Ausnahmen ausgelöst werden, automatisch vom **neue**. Wenn Sie Ihre eigenen Arbeitsspeicher-Funktionen schreiben, `malloc`für das Beispiel, dann können Sie für das Auslösen von Ausnahmen für Speicher verantwortlich sind.

Weitere Informationen zu `CMemoryException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException

Erstellt ein `CMemoryException`-Objekt.

```
CMemoryException();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Diese globale Funktion kann in einer Out-of-Memory-Situation erfolgreich ausgeführt werden, da es das Ausnahmeobjekt in zuvor zugeordnete Arbeitsspeicher erstellt. Weitere Informationen zur ausnahmeverarbeitung finden Sie im Artikel [Ausnahmen](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[CException-Klasse](cexception-class.md)<br/>
[Hierarchiediagramm](../hierarchy-chart.md)
