---
title: Cfontholder-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 04de8141469f82bdd1fbb6adc1bae94d6026324c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506442"
---
# <a name="cfontholder-class"></a>Cfontholder-Klasse

Implementiert die vordefinierte Schriftarteigenschaft und kapselt die Funktionalität eines Windows-Schriftartobjekts und der `IFont` -Schnittstelle.

## <a name="syntax"></a>Syntax

```
class CFontHolder
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|Erstellt ein `CFontHolder`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|Ruft die Zeichenfolge ab, die im Eigenschaften Browser eines Containers angezeigt wird.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Gibt die- `IDispatch` Schnittstelle der Schriftart zurück.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Gibt ein Handle für eine Windows-Schriftart zurück.|
|[CFontHolder::InitializeFont](#initializefont)|Initialisiert ein `CFontHolder` -Objekt.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Ruft Informationen für die zugehörige Schriftart ab.|
|[CFontHolder::ReleaseFont](#releasefont)|Trennt das `CFontHolder` -Objekt von den `IFont` Schnitt `IFontNotification` stellen und.|
|[CFontHolder::Select](#select)|Wählt eine Schriftart Ressource in einen Gerätekontext aus.|
|[CFontHolder::SetFont](#setfont)|Verbindet das `CFontHolder` -Objekt mit `IFont` einer-Schnittstelle.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|Ein Zeiger auf die `CFontHolder` - `IFont` Schnittstelle des Objekts.|

## <a name="remarks"></a>Hinweise

`CFontHolder`weist keine Basisklasse auf.

Verwenden Sie diese Klasse, um benutzerdefinierte Schriftart Eigenschaften für das Steuerelement zu implementieren. Weitere Informationen zum Erstellen solcher Eigenschaften finden Sie im Artikel [ActiveX-Steuerelemente: Verwenden von](../../mfc/mfc-activex-controls-using-fonts.md)Schriftarten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CFontHolder`

## <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

##  <a name="cfontholder"></a>Cfonthälter:: cfontholder

Erstellt ein `CFontHolder`-Objekt.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Parameter

*pNotify*<br/>
Ein Zeiger auf die- `IPropertyNotifySink` Schnittstelle der Schriftart.

### <a name="remarks"></a>Hinweise

Sie müssen aufzurufen `InitializeFont` , um das resultierende Objekt zu initialisieren, bevor Sie es verwenden.

##  <a name="getdisplaystring"></a>Cfonthälter:: GetDisplayString

Ruft eine Zeichenfolge ab, die im Eigenschaften Browser eines Containers angezeigt werden kann.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parameter

*strValue*<br/>
Verweis auf das [CString-Zeichen](../../atl-mfc-shared/reference/cstringt-class.md) , das die Anzeige Zeichenfolge enthalten soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Zeichenfolge erfolgreich abgerufen wird. andernfalls 0.

##  <a name="getfontdispatch"></a>Cfonthälter:: getfontdispatch

Rufen Sie diese Funktion auf, um einen Zeiger auf die Dispatchschnittstelle der Schriftart abzurufen.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `CFontHolder` - `IFontDisp` Schnittstelle des Objekts. Beachten Sie, dass die Funktion `GetFontDispatch` , die `IUnknown::Release` aufruft, auf diesem Schnittstellen Zeiger aufrufen muss, wenn Sie damit abgeschlossen ist.

### <a name="remarks"></a>Hinweise

Aufruf `InitializeFont` vor dem `GetFontDispatch`Aufrufen von.

##  <a name="getfonthandle"></a>Cfonthälter:: getfonthandle

Mit dieser Funktion können Sie ein Handle für eine Windows-Schriftart abrufen.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parameter

*cyLogical*<br/>
Die Höhe des Rechtecks in logischen Einheiten, in dem das Steuerelement gezeichnet wird.

*cyHimetric*<br/>
Die Höhe des Steuer Elements in MM_HIMETRIC Einheiten.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Schriftart Objekt. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Das Verhältnis von *cylogical* und *cyhimetric* wird verwendet, um die richtige Anzeige Größe in logischen Einheiten für die in MM_HIMETRIC Units ausgedrückte Schriftart Größe der Schriftart zu berechnen:

Anzeige Größe = ( *cylogical* / *cyhimetric*) X Schriftgröße

Die Version ohne Parameter gibt ein Handle für eine Schriftart zurück, die für den Bildschirm korrekt ist.

##  <a name="initializefont"></a>Cfonthälter:: initializefont

Initialisiert ein `CFontHolder` -Objekt.

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parameter

*pFontDesc*<br/>
Zeiger auf eine Schriftart Beschreibungs Struktur ( [fontdebug](/windows/win32/api/olectl/ns-olectl-fontdesc)), die die Merkmale der Schriftart angibt.

*pFontDispAmbient*<br/>
Ein Zeiger auf die Ambient-Schriftart Eigenschaft des Containers.

### <a name="remarks"></a>Hinweise

Wenn *pfontdispambient* nicht NULL ist, wird `CFontHolder` das Objekt mit `IFont` einem Klon der Schnittstelle verbunden, die von der ambient-Schriftart Eigenschaft des Containers verwendet wird.

Wenn *pfontdispambient* den Wert NULL hat, wird ein neues Schriftart Objekt entweder aus der Schriftart Beschreibung erstellt, auf die von *pfontabsc* verwiesen wird, oder, wenn *pfontabsc* NULL ist, von einer Standardbeschreibung.

Ruft diese Funktion nach dem Erstellen `CFontHolder` eines-Objekts auf.

##  <a name="m_pfont"></a>Cfonthälter:: m_pFont

Ein Zeiger auf die `CFontHolder` - `IFont` Schnittstelle des Objekts.

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

Ruft Informationen über die physische Schriftart ab, die durch `CFontHolder` das-Objekt dargestellt wird.

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Parameter

*lptm*<br/>
Ein Zeiger auf eine [textmetrikstruktur](/windows/win32/api/wingdi/ns-wingdi-textmetricw) , die die Informationen empfängt.

##  <a name="releasefont"></a>Cfonthälter:: releasefont

Diese Funktion trennt das `CFontHolder` -Objekt `IFont` von der-Schnittstelle.

```
void ReleaseFont();
```

##  <a name="select"></a>Cfontholder:: SELECT

Mit dieser Funktion können Sie die Schriftart Ihres Steuer Elements in den angegebenen Gerätekontext auswählen.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Der Gerätekontext, in dem die Schriftart ausgewählt wird.

*cyLogical*<br/>
Die Höhe des Rechtecks in logischen Einheiten, in dem das Steuerelement gezeichnet wird.

*cyHimetric*<br/>
Die Höhe des Steuer Elements in MM_HIMETRIC Einheiten.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Schriftart, die ersetzt wird.

### <a name="remarks"></a>Hinweise

Eine Erörterung der Parameter *cylogical* und *cyhimetric* finden Sie unter [getfonthandle](#getfonthandle) .

##  <a name="setfont"></a>Cfonthälter:: SetFont

Gibt jede vorhandene Schriftart frei und verbindet `CFontHolder` das Objekt mit `IFont` einer Schnittstelle.

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Parameter

*pNewFont*<br/>
Ein Zeiger auf die `IFont` neue-Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange-Klasse](../../mfc/reference/cpropexchange-class.md)
