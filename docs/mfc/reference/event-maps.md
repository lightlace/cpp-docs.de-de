---
title: Ereigniszuordnungen
ms.date: 06/20/2018
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: 512170d7eaa891b3616ca1ea56c29a8bb5cccda9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492235"
---
# <a name="event-maps"></a>Ereigniszuordnungen

Wenn möchte, dass ein Steuerelement seinem Container zu benachrichtigen, den eine Aktion, die (vom Steuerelemententwickler bestimmt) (z. B. eine Tastatureingabe, klicken mit der Maus oder eine Änderung an den Zustand des Steuerelements) aufgetreten sind, ruft er eine Funktion für die Ereignisse auslösen. Diese Funktion teilt den Steuerelementcontainer, den eine wichtige Aktion aufgetreten ist, durch Auslösen des entsprechenden Ereignisses.

Die Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, das zum Auslösen von Ereignissen optimiert. In diesem Modell "ereigniszuordnungen" werden verwendet, um zu bestimmen, welche Funktionen die Ereignisse für ein bestimmtes Steuerelement ausgelöst werden. Ereigniszuordnungen enthalten ein Makro für jedes Ereignis. Eine Event-Zuordnung auslöst, z. B. eine Aktie auf Ereignis wie folgt aussehen kann:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

Die `EVENT_STOCK_CLICK` -Makro gibt an, dass das Steuerelement eine Aktie auf, die jedes Mal, wenn er erkennt, dass eine Maus-Klickereignis ausgelöst wird. Eine ausführlichere Liste der anderen vordefinierten Ereignissen werden soll, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md). Makros sind auch verfügbar, um benutzerdefinierte Ereignisse anzugeben.

Obwohl Event-Zuordnungsmakros wichtig sind, Sie in der Regel nicht diese direkt einfügen. Dies ist daran, dass das Fenster "Eigenschaften" ereigniszuordnung Einträge automatisch in den Quelldateien, erstellt Wenn Sie es verwenden, um die Ereignisse auslösen von Ereignissen Funktionen zugeordnet. Jedes Mal, die Sie verwenden möchten, bearbeiten oder Hinzufügen eines Eintrags Event-Zuordnung können Sie das Fenster "Eigenschaften".

Ereigniszuordnungen Unterstützung bietet MFC die folgenden Makros:

## <a name="event-map-macros"></a>Ereigniszuordnungs-Makros

### <a name="event-map-declaration-and-demarcation"></a>Ereignis-Map-Deklaration und Demarkation

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|Deklariert, dass eine Event-Zuordnung in einer Klasse verwendet wird, Ereignisse, die die Ereignisse auslösen Funktionen zugeordnet (muss in der Klassendeklaration verwendet werden).|
|[BEGIN_EVENT_MAP](#begin_event_map)|Beginn der Definition eine Event-Zuordnung (muss in der klassenimplementierung verwendet werden).|
|[END_EVENT_MAP](#end_event_map)|Beendet die Definition eine Event-Zuordnung (muss in der klassenimplementierung verwendet werden).|

### <a name="event-mapping-macros"></a>Event-Zuordnung-Makros

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|Gibt an, welche Ereignisse auslösen-Funktion das angegebene Ereignis ausgelöst wird.|
|[EVENT_CUSTOM_ID](#event_custom_id)|Gibt an, welche Funktion – Auslösen von Ereignissen ausgelöst werden, das angegebene Ereignis mit einem angegebenen Dispatch-ID|

### <a name="message-mapping-macros"></a>Meldungszuordnungsmakros

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|Gibt an, einem benutzerdefinierten Verb, das von der OLE-Steuerelements behandelt.|
|[ON_STDOLEVERB](#on_stdoleverb)|Überschreibt eine standard-Verb-Zuordnung des OLE-Steuerelements.|

##  <a name="declare_event_map"></a>  DECLARE_EVENT_MAP

Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Event-Zuordnung zum Angeben von Ereignissen wird Ihr Steuerelement ausgelöst.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Hinweise

Verwenden Sie das DECLARE_EVENT_MAP-Makro, am Ende der Klassendeklaration. Klicken Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert verwenden Sie im BEGIN_EVENT_MAP-Makro Makroeinträge für die einzelnen Ereignisse des Steuerelements und dem END_EVENT_MAP-Makro, um das Ende der Ereignisliste zu deklarieren.

Weitere Informationen zu ereigniszuordnungen, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Anforderungen

**Header** afxctl.h

## <a name="begin_event_map"></a>  BEGIN_EVENT_MAP

Der Beginn der Definition der ereigniszuordnung.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Gibt an, dass der Name der Steuerelement-Klasse, dessen Ereignis eine Zuordnung, ist.

*Basisklasse*<br/>
Gibt den Namen der Basisklasse der *TheClass*.

### <a name="remarks"></a>Hinweise

Starten Sie in der Implementierungsdatei (.cpp), die die Member-Funktionen für die Klasse definiert die ereigniszuordnung mit dem BEGIN_EVENT_MAP-Makro, und klicken Sie dann fügen Sie die Makroeinträge für jedes der Ereignisse, und führen Sie die ereigniszuordnung mit dem END_EVENT_MAP-Makro.

Weitere Informationen zu ereigniszuordnungen und die BEGIN_EVENT_MAP-Makro, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Anforderungen

**Header** afxctl.h

##  <a name="end_event_map"></a>  END_EVENT_MAP

Verwenden Sie die END_EVENT_MAP-Makro, um die Definition der ereigniszuordnung zu beenden.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Anforderungen

**Header** afxctl.h

## <a name="event_custom"></a>  EVENT_CUSTOM

Definiert einen Eintrag für die Ereignis-Zuordnung für ein benutzerdefiniertes Ereignis.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Parameter

*pszName*<br/>
Der Name des Ereignisses.

*pfnFire*<br/>
Der Name der das Auslösen der Funktion des Ereignisses.

*vtsParams*<br/>
Eine durch Leerzeichen getrennte Liste von einer oder mehrerer Konstanten, die Parameterliste der Funktion angeben.

### <a name="remarks"></a>Hinweise

Die *VtsParams* Parameter ist eine durch Leerzeichen getrennte Liste von Werten aus der `VTS_` Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

Gibt eine Liste mit RGB darstellt 32-Bit-Ganzzahl Farbwert, gefolgt von einem Zeiger auf die `IFontDisp` -Schnittstelle eines Objekts der OLE-Schriftart.

Die `VTS_` Konstanten und ihre Bedeutungen lauten wie folgt:

|Symbol|Parametertyp|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|WÄHRUNG|
|VTS_DATE|DATE|
|VTS_BSTR|**const** __Char\*__|
|VTS_DISPATCH|LPDISPATCH|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|HANDLE|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_OPTEXCLUSIVE|OLE_OPTEXCLUSIVE|
|VTS_PICTURE|`IPictureDisp*`|
|VTS_TRISTATE|OLE_TRISTATE|
|VTS_XPOS_PIXELS|OLE_XPOS_PIXELS|
|VTS_YPOS_PIXELS|OLE_YPOS_PIXELS|
|VTS_XSIZE_PIXELS|OLE_XSIZE_PIXELS|
|VTS_YSIZE_PIXELS|OLE_YSIZE_PIXELS|
|TS_XPOS_HIMETRIC|OLE_XPOS_HIMETRIC|
|VTS_YPOS_HIMETRIC|OLE_YPOS_HIMETRIC|
|VTS_XSIZE_HIMETRIC|OLE_XSIZE_HIMETRIC|
|VTS_YSIZE_HIMETRIC|OLE_YSIZE_HIMETRIC|

> [!NOTE]
> Für alle variant-Typen, mit Ausnahme von VTS_FONT und VTS_PICTURE, wurden zusätzliche variant Konstanten definiert, die einen Zeiger auf die Konstante variant-Daten bereitstellen. Diese Konstanten werden mit dem Namen mit den `VTS_Pconstantname` Konvention. VTS_PCOLOR ist z. B. ein Zeiger auf eine VTS_COLOR-Konstante.

### <a name="requirements"></a>Anforderungen

**Header** afxctl.h

## <a name="event_custom_id"></a>  EVENT_CUSTOM_ID

Definiert ein Ereignis auslösen der Funktion für ein benutzerdefiniertes Ereignis aus, um die Dispatch-ID gemäß gehören *Dispid*.

```cpp
EVENT_CUSTOM_ID(
  pszName,
  dispid,
  pfnFire,
  vtsParams)
```

### <a name="parameters"></a>Parameter

*pszName*<br/>
Der Name des Ereignisses.

*DISPID*<br/>
Die Dispatch-ID, der vom Steuerelement verwendet wird, wenn das Ereignis ausgelöst wird.

*pfnFire*<br/>
Der Name der das Auslösen der Funktion des Ereignisses.

*vtsParams*<br/>
Eine Variable Liste von Parametern an den Steuerelementcontainer übergeben, wenn das Ereignis ausgelöst wird.

### <a name="remarks"></a>Hinweise

Die *VtsParams* Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der `VTS_` Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen nicht durch Kommas, gibt die Parameterliste der Funktion an. Zum Beispiel:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

Gibt eine Liste mit RGB darstellt 32-Bit-Ganzzahl Farbwert, gefolgt von einem Zeiger auf die `IFontDisp` -Schnittstelle eines Objekts der OLE-Schriftart.

Eine Liste mit den `VTS_` -Konstanten finden Sie [EVENT_CUSTOM](#event_custom).

### <a name="requirements"></a>Anforderungen

**Header** afxctl.h

## <a name="on_oleverb"></a>  ON_OLEVERB

Dieses Makro definiert einen Zuordnungseintrag für Nachrichten, der einen bestimmten Member-Funktion des Steuerelements ein benutzerdefiniertes Verb zugeordnet.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Parameter

*idsVerbName*<br/>
Die Zeichenfolgenressource-ID des Verbs Namen.

*memberFxn*<br/>
Die Funktion, die vom Framework aufgerufen, wenn das Verb aufgerufen wird.

### <a name="remarks"></a>Hinweise

Der Ressourcen-Editor kann verwendet werden, um benutzerdefinierte Verbnamen zu erstellen, die die Zeichenfolgentabelle hinzugefügt werden.

Der Funktionsprototyp für *MemberFxn* ist:

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

Die Werte der *LpMsg*, *hWndParent*, und *LpRect* Parameter stammen aus der entsprechenden Parameter des der `IOleObject::DoVerb` Member-Funktion.

### <a name="requirements"></a>Anforderungen

**Header** afxole.h

## <a name="on_stdoleverb"></a>  ON_STDOLEVERB

Verwenden Sie dieses Makro, um das Standardverhalten eines standard-Verbs zu überschreiben.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Der standard Verbindex für das Verb, das überschrieben wird.

*memberFxn*<br/>
Die Funktion, die vom Framework aufgerufen, wenn das Verb aufgerufen wird.

### <a name="remarks"></a>Hinweise

Der standard Verbindex weist das Format `OLEIVERB_`, gefolgt von einer Aktion. OLEIVERB_SHOW OLEIVERB_HIDE und OLEIVERB_UIACTIVATE sind einige Beispiele für die standard-Verben.

Finden Sie unter [ON_OLEVERB](#on_oleverb) eine Beschreibung der Funktionsprototyp als verwendet werden soll die *MemberFxn* Parameter.

### <a name="requirements"></a>Anforderungen

**Header** afxole.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
