---
title: COleDispatchDriver-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da7093d25e8221ce3fc3ec8d0d13f8bbc5b420d2
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821321"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver-Klasse

Implementiert die Clientseite der OLE-Automatisierung.

## <a name="syntax"></a>Syntax

```
class COleDispatchDriver
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Erstellt ein `COleDispatchDriver`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Fügt eine `IDispatch` Verbindung mit der `COleDispatchDriver` Objekt.|
|[COleDispatchDriver:: CreateDispatch](#createdispatch)|Erstellt eine `IDispatch` Verbindung und fügt es der `COleDispatchDriver` Objekt.|
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Trennt eine `IDispatch` -Verbindung nicht freigegeben wurde.|
|[COleDispatchDriver:: GetProperty](#getproperty)|Ruft ein Automatisierungseigenschaft ab.|
|[COleDispatchDriver:: InvokeHelper](#invokehelper)|Hilfsmethode zum Aufrufen von Automatisierungsmethoden.|
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Versionen einer `IDispatch` Verbindung.|
|[Schlüsselwörter COleDispatchDriver:: SetProperty](#setproperty)|Legt eine Automatisierungseigenschaft fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::operator =](#operator_eq)|Kopiert den Quellwert in die `COleDispatchDriver` Objekt.|
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|Greift auf die zugrunde liegende `IDispatch` Zeiger.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Gibt an, ob die Version der `IDispatch` während `ReleaseDispatch` oder Zerstörung von Objekten.|
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|Gibt an, der Zeiger auf die `IDispatch` Schnittstelle angefügte `COleDispatchDriver`.|

## <a name="remarks"></a>Hinweise

`COleDispatchDriver` eine Basisklasse keinen.

OLE-Dispatch-Schnittstellen bieten Zugriff auf Methoden und Eigenschaften eines Objekts. Memberfunktionen der `COleDispatchDriver` anfügen, trennen, erstellen und Freigeben eine Dispatch-Verbindung vom Typ `IDispatch`. Andere Memberfunktionen Variablenargumentlisten verwenden Sie zur Vereinfachung der Aufruf `IDispatch::Invoke`.

Diese Klasse kann direkt verwendet werden, aber es ist im Allgemeinen verwendet, nur von Klassen, die durch den Assistenten zum Hinzufügen von Klassen erstellt. Wenn Sie neue C++-Klassen durch Importieren einer Typbibliothek erstellen, werden die neuen Klassen von abgeleitet `COleDispatchDriver`.

Weitere Informationen zur Verwendung von `COleDispatchDriver`, finden Sie unter den folgenden Artikeln:

- [Automatisierungsclients](../../mfc/automation-clients.md)

- [Automatisierungsserver](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`COleDispatchDriver`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch

Rufen Sie die `AttachDispatch` -Memberfunktion auf, um dem `IDispatch` -Objekt einen `COleDispatchDriver` -Zeiger anzufügen. Weitere Informationen finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parameter

*lpDispatch*<br/>
Zeiger auf ein `IDispatch` -OLE-Objekt, der an das `COleDispatchDriver` -Objekt angefügt werden soll.

*bAutoRelease*<br/>
Gibt an, ob die Verteilung freigegeben werden soll, wenn dieses Objekt den Gültigkeitsbereich verlässt.

### <a name="remarks"></a>Hinweise

Diese Funktion gibt alle `IDispatch` -Zeiger zurück, die dem `COleDispatchDriver` -Objekt bereits angefügt wurden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>  COleDispatchDriver::COleDispatchDriver

Erstellt ein `COleDispatchDriver`-Objekt.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parameter

*lpDispatch*<br/>
Zeiger auf ein `IDispatch` -OLE-Objekt, der an das `COleDispatchDriver` -Objekt angefügt werden soll.

*bAutoRelease*<br/>
Gibt an, ob die Verteilung freigegeben werden soll, wenn dieses Objekt den Gültigkeitsbereich verlässt.

*dispatchSrc*<br/>
Ein Verweis auf ein vorhandenes `COleDispatchDriver` Objekt.

### <a name="remarks"></a>Hinweise

Das Formular `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **"bool"**`bAutoRelease` = **"true"**) verbindet die [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) Schnittstelle.

Das Formular `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) kopiert eine vorhandene `COleDispatchDriver` Objekt aus, und den Verweiszähler erhöht.

Das Formular `COleDispatchDriver`() erstellt eine `COleDispatchDriver` Objekt aber keine Verbindung her die `IDispatch` Schnittstelle. Vor der Verwendung von `COleDispatchDriver`(ohne Argumente), sollten Sie eine Verbindung eine `IDispatch` , indem Sie entweder [COleDispatchDriver:: CreateDispatch](#createdispatch) oder [COleDispatchDriver::AttachDispatch](#attachdispatch). Weitere Informationen finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](#createdispatch).

##  <a name="createdispatch"></a>  COleDispatchDriver:: CreateDispatch

Erstellt eine [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) -Schnittstellenobjekt und fügt es der `COleDispatchDriver` Objekt.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Die Klassen-ID, des zu erstellenden `IDispatch` -Verbindungsobjekts.

*pError*<br/>
Ein Zeiger auf ein OLE-Ausnahmeobjekt, das den Statuscode aufnimmt, der sich durch die Erstellung ergibt.

*lpszProgID*<br/>
Ein Zeiger auf den programmgesteuerten Bezeichner, z. B. „Excel.Document.5“, des Automatisierungsobjekts, für das das Dispatch-Objekt erstellt werden soll.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch

Trennt die aktuelle `IDispatch` Verbindung aus diesem Objekt.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die zuvor angefügte OLE `IDispatch` Objekt.

### <a name="remarks"></a>Hinweise

Die `IDispatch` wird nicht freigegeben.

Weitere Informationen zu den LPDISPATCH-Typ, finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>  COleDispatchDriver:: GetProperty

Ruft die Objekteigenschaft, die anhand des *DwDispID*.

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Bezeichnet die Eigenschaft abgerufen werden sollen.

*vtProp*<br/>
Gibt die Eigenschaft abgerufen werden sollen. Mögliche Werte finden Sie im Abschnitt "Hinweise" für [COleDispatchDriver:: InvokeHelper](#invokehelper).

*pvProp*<br/>
Die Adresse der Variablen, die den Wert der Eigenschaft erhält. Es muss den vom angegebenen Typ übereinstimmen *VtProp*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>  COleDispatchDriver:: InvokeHelper

Ruft die Objektmethode oder Eigenschaft, die anhand des *DwDispID*, in dem vom angegebenen Kontext *wFlags*.

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Bezeichnet die aufzurufende Methode oder Eigenschaft.

*wFlags*<br/>
Flags, die den Kontext des Aufrufs von beschreiben `IDispatch::Invoke`. sein. Eine Liste der möglichen Werte, finden Sie unter den *wFlags* Parameter im [IDispatch:: Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) im Windows SDK.

*vtRet*<br/>
Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt „Hinweise“.

*pvRet*<br/>
Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Es muss den vom angegebenen Typ übereinstimmen *VtRet*.

*pbParamInfo*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge von Bytes, die den Objekttyp die folgenden Parameter angeben *PbParamInfo*.

*...*<br/>
Variable Parameterliste, der in der angegebenen Typen *PbParamInfo*.

### <a name="remarks"></a>Hinweise

Die *PbParamInfo* Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter. Die variable Argumentliste wird in der Syntaxdeklaration durch **...** dargestellt.

Mögliche Werte für die *VtRet* Argument stammen aus der Enumeration VARENUM. Folgende Werte sind möglich:

|Symbol|Rückgabetyp|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**DATE**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**VARIANT**|
|VT_UNKNOWN|LPUNKNOWN|

Die *PbParamInfo* Argument ist eine durch Leerzeichen getrennte Liste von **VTS_** Konstanten. Einer oder mehrere dieser Werte, durch Leerzeichen (nicht Kommas) getrennt, gibt bzw. geben die Parameterliste der Funktion an. Mögliche Werte sind aufgeführt, mit der [EVENT_CUSTOM](event-maps.md#event_custom) Makro.

Diese Funktion konvertiert die Parameter auf VARIANTARG-Werte und ruft anschließend die [IDispatch:: Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Methode. Bei einem Fehler des Aufrufs von `Invoke` löst diese Funktion eine Ausnahme aus. Wenn die SCODE (Statuscode) von zurückgegeben `IDispatch::Invoke` DISP_E_EXCEPTION, ist diese Funktion löst eine [COleException](../../mfc/reference/coleexception-class.md) Objekt; andernfalls löst eine [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).

Weitere Informationen finden Sie unter [VARIANTARG](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [IDispatch:: Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke), und [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) in das Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](#createdispatch).

##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease

Bei "true", Zugriff auf das COM-Objekt durch [M_lpDispatch](#m_lpdispatch) automatisch freigegeben, wenn [ReleaseDispatch](#releasedispatch) aufgerufen wird oder wenn dies `COleDispatchDriver` -Objekt zerstört wird.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `m_bAutoRelease` im Konstruktor auf TRUE festgelegt ist.

Weitere Informationen zum Freigeben von COM-Objekten, finden Sie unter [Verweiszählung implementieren](/windows/desktop/com/implementing-reference-counting) und [IUnknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch

Der Zeiger auf die `IDispatch` Schnittstelle angefügte `COleDispatchDriver`.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Hinweise

Die `m_lpDispatch` -Datenmember ist eine öffentliche Variable des Typs LPDISPATCH.

Weitere Informationen finden Sie unter [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleDispatchDriver::AttachDispatch](#attachdispatch).

##  <a name="operator_eq"></a>  COleDispatchDriver::operator =

Kopiert den Quellwert in die `COleDispatchDriver` Objekt.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parameter

*dispatchSrc*<br/>
Ein Zeiger auf eine vorhandene `COleDispatchDriver` Objekt.

##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH

Greift auf die zugrunde liegende `IDispatch` Zeiger, der die `COleDispatchDriver` Objekt.

```
operator LPDISPATCH();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch

Versionen der `IDispatch` Verbindung. Weitere Informationen finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Hinweise

Wenn Automatische Freigabe für diese Verbindung festgelegt wurde, ruft diese Funktion `IDispatch::Release` vor der Freigabe der Schnittstelle.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleDispatchDriver::AttachDispatch](#attachdispatch).

##  <a name="setproperty"></a>  Schlüsselwörter COleDispatchDriver:: SetProperty

Legt die OLE-Objekteigenschaft gemäß *DwDispID*.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die festzulegende Eigenschaft an.

*vtProp*<br/>
Gibt den Typ der festzulegenden Eigenschaft an. Mögliche Werte finden Sie im Abschnitt "Hinweise" für [COleDispatchDriver:: InvokeHelper](#invokehelper).

*...*<br/>
Einen einzelnen Parameter des Typs vom angegebenen *VtProp*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CALCDRIV](../../visual-cpp-samples.md)<br/>
[MFC ACDUAL-Beispiel](../../visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
