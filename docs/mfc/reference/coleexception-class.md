---
title: COleException-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
ms.openlocfilehash: 6874df550103abf727573d8e34b8adadd9643db8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767807"
---
# <a name="coleexception-class"></a>COleException-Klasse

Stellt eine Ausnahmebedingung dar, die sich auf einen OLE-Vorgang bezieht.

## <a name="syntax"></a>Syntax

```
class COleException : public CException
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleException::Process](#process)|Übersetzt eine abgefangene Ausnahme in einem OLE-Rückgabecode an.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleException::m_sc](#m_sc)|Enthält den Statuscode, der die Ursache der Ausnahme angibt.|

## <a name="remarks"></a>Hinweise

Die `COleException` Klasse enthält einen öffentlichen Datenmember, die den Statuscode, der angibt, der die Ursache der Ausnahme enthält.

Im Allgemeinen sollten Sie keine erstellen eine `COleException` Objekt direkt, sondern, rufen Sie [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Weitere Informationen zu Ausnahmen finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: OLE-Ausnahmen](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="m_sc"></a>  COleException::m_sc

Dieses Datenelement enthält die OLE-Statuscode, der den Grund für die Ausnahme angibt.

```
SCODE m_sc;
```

### <a name="remarks"></a>Hinweise

Der Wert dieser Variablen wird festgelegt, indem [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Weitere Informationen zu SCODE, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

##  <a name="process"></a>  COleException::Process

Rufen Sie die **Prozess** Memberfunktion versucht, eine abgefangene Ausnahme in eine OLE-Status-Code zu übersetzen.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>Parameter

*pAnyException*<br/>
Zeiger auf eine abgefangene Ausnahme.

### <a name="return-value"></a>Rückgabewert

Ein OLE-Statuscode.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Funktion ist **statische**.

Weitere Informationen zu SCODE, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe dazu das Beispiel für [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
