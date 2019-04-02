---
title: COleDispatchException-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 2d5b9d2a0dc1e716ea8cb20f0d0dcb4c5d765079
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769055"
---
# <a name="coledispatchexception-class"></a>COleDispatchException-Klasse

Behandelt Ausnahmen, die für die `IDispatch` -OLE-Schnittstelle (eine Schlüsselkomponente der OLE-Automatisierung) spezifisch sind.

## <a name="syntax"></a>Syntax

```
class COleDispatchException : public CException
```

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Der Hilfekontext für Fehler.|
|[COleDispatchException::m_strDescription](#m_strdescription)|Mündliche fehlerbeschreibung.|
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Die Hilfedatei für die Verwendung mit `m_dwHelpContext`.|
|[COleDispatchException::m_strSource](#m_strsource)|Anwendung, die die Ausnahme generiert hat.|
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-Fehlercode.|

## <a name="remarks"></a>Hinweise

Wie die anderen Ausnahmeklassen abgeleitet der `CException` -Basisklasse `COleDispatchException` mit die AUSLÖSEN, THROW_LAST, TRY, CATCH, AND_CATCH und END_CATCH-Makros verwendet werden kann.

Sie sollten im Allgemeinen Aufrufen [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) erstellen und Auslösen einer `COleDispatchException` Objekt.

Weitere Informationen zu Ausnahmen finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: OLE-Ausnahmen](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="m_dwhelpcontext"></a>  COleDispatchException::m_dwHelpContext

Identifiziert einen Hilfekontext, in der Hilfe von Ihrer Anwendung (. HLP)-Datei.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Hinweise

Dieser Member wird festgelegt, von der Funktion [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Wenn eine Ausnahme ausgelöst wird.

### <a name="example"></a>Beispiel

  Siehe dazu das Beispiel für [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_strdescription"></a>  COleDispatchException::m_strDescription

Enthält eine fehlerbeschreibung mündliche wie "Datenträger voll".

```
CString m_strDescription;
```

### <a name="remarks"></a>Hinweise

Dieser Member wird festgelegt, von der Funktion [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Wenn eine Ausnahme ausgelöst wird.

### <a name="example"></a>Beispiel

  Siehe dazu das Beispiel für [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_strhelpfile"></a>  COleDispatchException::m_strHelpFile

Das Framework füllt diese Zeichenfolge mit dem Namen der Hilfedatei von der Anwendung ab.

```
CString m_strHelpFile;
```

##  <a name="m_strsource"></a>  COleDispatchException::m_strSource

Das Framework füllt diese Zeichenfolge mit dem Namen der Anwendung, die die Ausnahme generiert hat.

```
CString m_strSource;
```

### <a name="example"></a>Beispiel

  Siehe dazu das Beispiel für [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_wcode"></a>  COleDispatchException::m_wCode

Enthält einen Fehlercode, der spezifisch für Ihre Anwendung an.

```
WORD m_wCode;
```

### <a name="remarks"></a>Hinweise

Dieser Member wird festgelegt, von der Funktion [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Wenn eine Ausnahme ausgelöst wird.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDispatchDriver-Klasse](../../mfc/reference/coledispatchdriver-class.md)<br/>
[COleException-Klasse](../../mfc/reference/coleexception-class.md)
