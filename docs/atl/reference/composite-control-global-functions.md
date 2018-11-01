---
title: Globale Funktionen zusammengesetzter Steuerelemente
ms.date: 11/04/2016
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
ms.openlocfilehash: d86978c6bf8aba87828cdda91c3e849a2f755a90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525267"
---
# <a name="composite-control-global-functions"></a>Globale Funktionen zusammengesetzter Steuerelemente

Diese Funktionen bieten Unterstützung für das Erstellen von Dialogfeldern, und klicken Sie zum Erstellen, hosten und Lizenzierung von ActiveX-Steuerelementen.

> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|Erstellt ein modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage. Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|Erstellt ein nicht modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage. Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Erstellt ein ActiveX-Steuerelement, initialisiert wird, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert wird, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|
|[AtlAxAttachControl](#atlaxattachcontrol)|Fügt ein bereits erstelltes Steuerelement an das angegebene Fenster an.|
|[AtlAxGetHost](#atlaxgethost)|Zum Abrufen von eines direkten Schnittstellenzeiger zu dem Container für ein bestimmtes Fenster (sofern vorhanden), anhand des Handles.|
|[AtlAxGetControl](#atlaxgetcontrol)|Verwendet, um einen direkten Schnittstellenzeiger auf das Steuerelement in einem angegebenen Fenster (sofern vorhanden) enthaltenen abzurufen anhand des Handles.|
|[AtlSetChildSite](#atlsetchildsite)|Initialisiert die `IUnknown` des untergeordneten Standorts.|
|[AtlAxWinInit](#atlaxwininit)|Initialisiert den Hostcode AxWin-Objekte.|
|[AtlAxWinTerm](#atlaxwinterm)|Hebt die Initialisierung des Codes zum Hosten für AxWin-Objekte.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Gibt Informationen über die standardquellschnittstelle eines Objekts zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** atlhost.h

##  <a name="atlaxdialogbox"></a>  AtlAxCreateDialog

Erstellt ein modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage.

```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>Parameter

*hInstance*<br/>
[in] Identifiziert eine Instanz des Moduls, deren ausführbare Datei der Dialogfeldvorlage enthält.

*lpTemplateName*<br/>
[in] Identifiziert die Dialogfeldvorlage. Dieser Parameter ist entweder der Zeiger auf eine Null-terminierte Zeichenfolge, die gibt den Namen der Dialogfeldvorlage oder ein ganzzahliger Wert, der angibt, den Ressourcenbezeichner, der die Dialogfeldvorlage. Wenn der Parameter einen Ressourcenbezeichner angegeben ist, dessen höherwertiges Wort muss 0 (null) sein, und seine niederwertige Wort muss den Bezeichner enthalten. Sie können die [MAKEINTRESOURCE](/windows/desktop/api/winuser/nf-winuser-makeintresourcea) Makro zum Erstellen dieses Werts.

*hWndParent*<br/>
[in] Gibt das Fenster, das Dialogfeld besitzt.

*lpDialogProc*<br/>
[in] Verweist auf die Dialogfeldprozedur. Weitere Informationen über die Dialogfeldprozedur finden Sie unter [DialogProc-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms645469).

*dwInitParam*<br/>
[in] Gibt den Wert zu übergeben, um das Dialogfeld in der *lParam* -Parameter der WM_INITDIALOG-Meldung.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Mit `AtlAxDialogBox` mit einer Dialogfeldvorlage, der ein ActiveX-Steuerelement enthält, geben Sie eine gültige CLSID "," APPID "oder" URL-Zeichenfolge als die *Text* Feld der **Steuerelement** Abschnitt der Dialogfeldressource, zusammen mit " AtlAxWin80 "als die *Klassenname* Feld im gleichen Abschnitt. Im folgenden wird veranschaulicht, was eine gültige **Steuerelement** Abschnitt könnte folgendermaßen aussehen:

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

Weitere Informationen zum Bearbeiten des Ressourcenskripts finden Sie unter [Vorgehensweise: Öffnen einer Ressourcenskriptdatei im Textformat](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Weitere Informationen zu Ressourcendefinition Anweisungen, finden Sie unter [allgemeine Steuerelementparameter](/windows/desktop/menurc/common-control-parameters) unter Windows SDK *: SDK Tools*.

Weitere Informationen zu Dialogfeldern, die im Allgemeinen finden Sie unter [Dialogfeld](/windows/desktop/api/winuser/nf-winuser-dialogboxa) und [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) im Windows SDK.

##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog

Erstellt ein nicht modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage.

```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>Parameter

*hInstance*<br/>
[in] Identifiziert eine Instanz des Moduls, deren ausführbare Datei der Dialogfeldvorlage enthält.

*lpTemplateName*<br/>
[in] Identifiziert die Dialogfeldvorlage. Dieser Parameter ist entweder der Zeiger auf eine Null-terminierte Zeichenfolge, die gibt den Namen der Dialogfeldvorlage oder ein ganzzahliger Wert, der angibt, den Ressourcenbezeichner, der die Dialogfeldvorlage. Wenn der Parameter einen Ressourcenbezeichner angegeben ist, dessen höherwertiges Wort muss 0 (null) sein, und seine niederwertige Wort muss den Bezeichner enthalten. Sie können die [MAKEINTRESOURCE](/windows/desktop/api/winuser/nf-winuser-makeintresourcea) Makro zum Erstellen dieses Werts.

*hWndParent*<br/>
[in] Gibt das Fenster, das Dialogfeld besitzt.

*lpDialogProc*<br/>
[in] Verweist auf die Dialogfeldprozedur. Weitere Informationen über die Dialogfeldprozedur finden Sie unter [DialogProc-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms645469).

*dwInitParam*<br/>
[in] Gibt den Wert zu übergeben, um das Dialogfeld in der *lParam* -Parameter der WM_INITDIALOG-Meldung.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.

Finden Sie unter [CreateDialog](/windows/desktop/api/winuser/nf-winuser-createdialoga) und [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) in das Windows SDK.

##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl

Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:

- Eine ProgID, z. B. "MSCAL. Calendar.7 "

- Eine CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"

- Eine URL wie z. B. "http://www.microsoft.com"

- Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"

- Ein Fragment der HTML wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"

   > [!NOTE]
   > "MSHTML:" muss vor der HTML-Fragment stehen, damit es als einen MSHTML-Datenstrom festgelegt ist.

*hWnd*<br/>
[in] Handle für das Fenster, dem das Steuerelement zugeordnet wird.

*pStream*<br/>
[in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. NULL kann sein.

*ppUnkContainer*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des Containers. NULL kann sein.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Diese globale Funktion können Sie das gleiche Ergebnis wie das Aufrufen [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*Wert*, *hWnd*, *pStream*, NULL, NULL. NULL, NULL);.

Ein lizenziertes ActiveX-Steuerelement erstellen zu können, finden Sie unter [AtlAxCreateControlLic](#atlaxcreatecontrollic).

##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx

Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster. Weiterhin können ein Schnittstellenzeiger und eine Ereignissenke für das neue Steuerelement erstellt werden.

```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:

- Eine ProgID, z. B. "MSCAL. Calendar.7 "

- Eine CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"

- Eine URL wie z. B. "http://www.microsoft.com"

- Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"

- Ein Fragment der HTML wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"

   > [!NOTE]
   > "MSHTML:" muss vor der HTML-Fragment stehen, damit es als einen MSHTML-Datenstrom festgelegt ist.

*hWnd*<br/>
[in] Handle für das Fenster, dem das Steuerelement zugeordnet wird.

*pStream*<br/>
[in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. NULL kann sein.

*ppUnkContainer*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des Containers. NULL kann sein.

*ppUnkControl*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des erstellten Steuerelements. NULL kann sein.

*iidSink*<br/>
Der Schnittstellenbezeichner einer ausgehenden Schnittstelle für das enthaltene Objekt.

*punkSink*<br/>
Ein Zeiger auf die `IUnknown` -Schnittstelle des Senkenobjekts an den Verbindungspunkt, der anhand des verbunden sein, *IidSink* auf das enthaltene Objekt, nachdem das enthaltene Objekt wurde erfolgreich erstellt wurde.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

`AtlAxCreateControlEx` ist vergleichbar mit [AtlAxCreateControl](#atlaxcreatecontrol) ermöglicht aber auch einen Schnittstellenzeiger auf das neu erstellte Steuerelement zu empfangen, und richten Sie eine Ereignissenke, zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.

Ein lizenziertes ActiveX-Steuerelement erstellen zu können, finden Sie unter [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).

##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic

Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:

- Eine ProgID, z. B. "MSCAL. Calendar.7 "

- Eine CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"

- Eine URL wie z. B. "http://www.microsoft.com"

- Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"

- Ein Fragment der HTML wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"

   > [!NOTE]
   > "MSHTML:" muss vor der HTML-Fragment stehen, damit es als einen MSHTML-Datenstrom festgelegt ist.

*hWnd*<br/>
Handle für das Fenster, dem das Steuerelement zugeordnet wird.

*pStream*<br/>
Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. NULL kann sein.

*ppUnkContainer*<br/>
Die Adresse eines Zeigers, der erhält die `IUnknown` des Containers. NULL kann sein.

*bstrLic*<br/>
BSTR, das die Lizenz für das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) ein Beispiel zur Verwendung `AtlAxCreateControlLic`.

##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx

Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster. Weiterhin können ein Schnittstellenzeiger und eine Ereignissenke für das neue Steuerelement erstellt werden.

```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:

- Eine ProgID, z. B. "MSCAL. Calendar.7 "

- Eine CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"

- Eine URL wie z. B. "http://www.microsoft.com"

- Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"

- Ein Fragment der HTML wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"

   > [!NOTE]
   > "MSHTML:" muss vor der HTML-Fragment stehen, damit es als einen MSHTML-Datenstrom festgelegt ist.

*hWnd*<br/>
Handle für das Fenster, dem das Steuerelement zugeordnet wird.

*pStream*<br/>
Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. NULL kann sein.

*ppUnkContainer*<br/>
Die Adresse eines Zeigers, der erhält die `IUnknown` des Containers. NULL kann sein.

*ppUnkControl*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des erstellten Steuerelements. NULL kann sein.

*iidSink*<br/>
Der Schnittstellenbezeichner einer ausgehenden Schnittstelle für das enthaltene Objekt.

*punkSink*<br/>
Ein Zeiger auf die `IUnknown` -Schnittstelle des Senkenobjekts an den Verbindungspunkt, der anhand des verbunden sein, *IidSink* auf das enthaltene Objekt, nachdem das enthaltene Objekt wurde erfolgreich erstellt wurde.

*bstrLic*<br/>
BSTR, das die Lizenz für das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

`AtlAxCreateControlLicEx` ist vergleichbar mit [AtlAxCreateControlLic](#atlaxcreatecontrollic) ermöglicht aber auch einen Schnittstellenzeiger auf das neu erstellte Steuerelement zu empfangen, und richten Sie eine Ereignissenke, zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) ein Beispiel zur Verwendung `AtlAxCreateControlLicEx`.

##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl

Fügt ein bereits erstelltes Steuerelement an das angegebene Fenster an.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parameter

*pControl*<br/>
[in] Ein Zeiger auf die `IUnknown` des Steuerelements.

*hWnd*<br/>
[in] Handle für das Fenster, das das Steuerelement hostet.

*ppUnkContainer*<br/>
[out] Ein Zeiger auf einen Zeiger auf die `IUnknown` des Containerobjekts.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Verwendung [AtlAxCreateControlEx](#atlaxcreatecontrolex) und [AtlAxCreateControl](#atlaxcreatecontrol) gleichzeitig erstellen, und fügen Sie ein Steuerelement.

> [!NOTE]
>  Das Steuerelementobjekt anzufügende muss korrekt initialisiert werden, vor dem Aufruf `AtlAxAttachControl`.

##  <a name="atlaxgethost"></a>  AtlAxGetHost

Ruft anhand eines bestimmten Fensters einen direkten Schnittstellenzeiger zu dem Container für das Fenster (sofern vorhanden) ab.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parameter

*h*<br/>
[in] Ein Handle für das Fenster, das das Steuerelement gehostet wird.

*PP*<br/>
[out] Die `IUnknown` des Containers des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl

Ruft anhand des Handles eines angegebenen Fensters einen direkten Schnittstellenzeiger zu dem Steuerelement ab, das in dem Fenster enthalten ist.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parameter

*h*<br/>
[in] Ein Handle für das Fenster, das das Steuerelement gehostet wird.

*PP*<br/>
[out] Die `IUnknown` des gehosteten Steuerelements.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="atlsetchildsite"></a>  AtlSetChildSite

Mit dieser Funktion können Sie den Standort des untergeordneten Objekts zum Festlegen der `IUnknown` des übergeordneten Objekts.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>Parameter

*punkChild*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle des untergeordneten Elements.

*punkParent*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle des übergeordneten Elements.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="atlaxwininit"></a>  AtlAxWinInit

Diese Funktion initialisiert den ATLs Steuerelements durch Registrierung der **"AtlAxWin80"** und **"AtlAxWinLic80"** Fensterklassen sowie einer Reihe von benutzerdefinierten fenstermeldungen.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung des Steuerelements Hostcode erfolgreich war; andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Funktion muss aufgerufen werden, bevor Sie mit dem ATL-Steuerelement, das hosting-API. Nach einem Aufruf dieser Funktion die **"AtlAxWin"** Window-Klasse kann verwendet werden, in Aufrufen von [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) oder [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)gemäß der Beschreibung in das Windows SDK.

##  <a name="atlaxwinterm"></a>  AtlAxWinInit

Diese Funktion hebt die Initialisierung ATLs Steuerelements durch Aufheben der Registrierung der **"AtlAxWin80"** und **"AtlAxWinLic80"** Fensterklassen.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft einfach [UnregisterClass](https://msdn.microsoft.com/library/windows/desktop/ms644899) wie beschrieben in das Windows SDK.

Rufen Sie diese Funktion zu bereinigen, nachdem alle vorhandenen Hostfenster zerstört wurden, wenn Sie aufgerufen [AtlAxWinInit](#atlaxwininit) und Sie nicht mehr benötigen, um Host-Windows zu erstellen. Wenn Sie diese Funktion nicht aufrufen, werden die Fensterklasse aufgehoben automatisch beim Beenden des Prozesses.

##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface

Mit dieser Funktion werden Informationen über die Standardquellschnittstelle eines Objekts abgerufen.

```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```

### <a name="parameters"></a>Parameter

*punkObj*<br/>
[in] Ein Zeiger auf das Objekt für die Informationen zurückgegeben werden soll.

*plibid*<br/>
[out] Ein Zeiger auf die LIBID der Typbibliothek, die die Definition der Quellschnittstelle enthält.

*piid*<br/>
[out] Ein Zeiger auf die Schnittstellen-ID des Objekts Standard-Quellschnittstelle.

*pdwMajor*<br/>
[out] Ein Zeiger auf die Hauptversionsnummer der Typbibliothek, die die Definition der Quellschnittstelle enthält.

*pdwMinor*<br/>
[out] Ein Zeiger auf die Nebenversionsnummer der Typbibliothek, die die Definition der Quellschnittstelle enthält.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

`AtlGetObjectSourceInterface` können Sie mit der Schnittstellen-ID des Standard-Quellschnittstelle, sowie die LIBID und umfangreichen und Nebenversionsnummern der Typbibliothek, die diese Schnittstelle beschreibt bereitstellen.

> [!NOTE]
>  Für diese Funktion erfolgreich die angeforderte Informationen abgerufen werden soll, wird das Objekt durch dargestellt *PunkObj* müssen implementieren `IDispatch` (und Zurückgeben von Informationen über `IDispatch::GetTypeInfo`) plus, muss außerdem entweder implementieren`IProvideClassInfo2` oder `IPersist`. Die Typinformationen für die Quellschnittstelle muss in der gleichen Typbibliothek als die Typinformationen für `IDispatch`.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie der Klasse eine Ereignissenke, definieren möglicherweise `CEasySink`, reduzieren die Anzahl der Argumente, die Sie an übergeben können `IDispEventImpl` , die absolut erforderlichen Funktionen. `EasyAdvise` und `EasyUnadvise` verwenden `AtlGetObjectSourceInterface` zum Initialisieren der [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) Member vor dem Aufruf [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) oder [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)<br/>
[Makros zusammengesetzter Steuerelemente](../../atl/reference/composite-control-macros.md)
