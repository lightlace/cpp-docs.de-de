---
title: CInvalidArgException-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
dev_langs:
- C++
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff0727f1d194982ad76d24b0a91875448ea45c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389804"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException-Klasse

Diese Klasse stellt eine Ausnahmebedingung für ein ungültiges Argument dar.

## <a name="syntax"></a>Syntax

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Der Konstruktor.|

## <a name="remarks"></a>Hinweise

Ein `CInvalidArgException` -Objekt stellt eine Ausnahmebedingung Ungültiges Argument dar.

Weitere Informationen zu Exception Handling, finden Sie unter den [CException-Klasse](../../mfc/reference/cexception-class.md) Thema und [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException

Der Konstruktor.

```
CInvalidArgException();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Konstruktor nicht direkt. Rufen Sie die globale Funktion **AfxThrowInvalidArgException**.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException-Klasse](../../mfc/reference/csimpleexception-class.md)
