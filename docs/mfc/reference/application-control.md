---
title: Anwendungssteuerelement
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: e4944c1cf1114bbd009ebc62b776628ba86b3b4d
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850310"
---
# <a name="application-control"></a>Anwendungssteuerelement

OLE erfordert erhebliche Kontrolle über die Anwendungen und ihre Objekte. Die OLE-System-DLLs muss Lage starten und automatische Veröffentlichung von Anwendungen, koordinieren die Produktion und Ändern von Objekten und so weiter. Die Funktionen in diesem Thema werden diese Anforderungen erfüllen. Zusätzlich zu der durch die OLE-System-DLLs aufgerufen wird, müssen diese Funktionen manchmal von Anwendungen sowie aufgerufen werden.

### <a name="application-control"></a>Anwendungssteuerelement

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|Gibt an, ob die Anwendung beendet werden kann.|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Ruft die aktuelle Nachricht Anwendungsfilter ab.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Ruft das Flag der aktuellen Benutzersteuerelement ab.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Löscht das Benutzersteuerelement-Flag ab oder legt diese fest.|
|[AfxOleLockApp](#afxolelockapp)|Erhöht die Framework global-Zähler für die Anzahl von aktiven Objekten in einer Anwendung.|
|[AfxOleLockControl](#afxolelockcontrol)| Sperrt die Klassenfactory des angegebenen Steuerelements. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Verringert die Framework Anzahl der von aktiven Objekten in einer Anwendung.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Entsperrt die Klassenfactory des angegebenen Steuerelements. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Einen Server registriert in der systemregistrierung OLE.|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Implementiert die Benutzeroberfläche für die *Typename* Objekt-Befehl.|

##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp

Gibt an, ob die Anwendung beendet werden kann.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Anwendung beendet werden kann; andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Anwendung sollte nicht beenden, wenn ausstehende Verweise auf seine Objekte vorhanden sind. Die globalen Funktionen `AfxOleLockApp` und `AfxOleUnlockApp` Inkrementieren und Dekrementieren, bzw. einen Zähler von Verweisen auf Objekte von der Anwendung. Die Anwendung sollte nicht beendet, wenn dieser Leistungsindikator ungleich NULL ist. Wenn der Zähler ungleich NULL ist, wird das Hauptfenster der Anwendung (nicht zerstörte) ausgeblendet, wenn der Benutzer schließen aus dem Systemmenü oder beenden, die über das Menü Datei wählt. Das Framework ruft diese Funktion `CFrameWnd::OnClose`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter

Ruft die aktuelle Nachricht Anwendungsfilter ab.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den aktuellen Nachrichtenfilter.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird für den Zugriff auf die aktuelle `COleMessageFilter`-Objekt, abgeleitet, wie Sie aufgerufen werden musste `AfxGetApp` auf das aktuelle Anwendungsobjekt zugreifen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>Anforderungen

**Header**: afxwin.h

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl

Ruft das Flag der aktuellen Benutzersteuerelement ab.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Benutzer Kontrolle über die Anwendung ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Benutzer ist im Steuerelement der Anwendung, wenn der Benutzer explizit geöffnet oder erstellt ein neues Dokument. Der Benutzer ist auch im Steuerelement, wenn die Anwendung durch die OLE-System-DLLs nicht gestartet wurde, das heißt, wenn der Benutzer die Anwendung mit der Shell des Betriebssystems gestartet.

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl

Legt fest oder löscht die Benutzersteuerelement-Flag, das in der Referenz für erläutert `AfxOleGetUserCtrl`.

```
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>Parameter

*bUserCtrl*<br/>
Gibt an, ob das Benutzersteuerelement Flag festgelegt oder gelöscht werden.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion, wenn der Benutzer erstellt oder ein Dokument lädt, aber nicht, wenn ein Dokument geladen oder über eine indirekte Aktion, z. B. das Laden eines eingebetteten Objekts aus einer containeranwendung erstellt wurden.

Rufen Sie diese Funktion, wenn andere Aktionen in Ihrer Anwendung den Benutzer Kontrolle über die Anwendung eingefügt werden soll.

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp

Erhöht die Framework global-Zähler für die Anzahl von aktiven Objekten in der Anwendung an.

```
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>Hinweise

Das Framework erfasst die Anzahl der die Anzahl der Objekte in einer Anwendung aktiv. Die `AfxOleLockApp` und `AfxOleUnlockApp` -Funktionen, die Inkrement- und Dekrement-diese Anzahl.

Wenn der Benutzer versucht, eine Anwendung zu schließen, die aktiven Objekte enthält, eine Anwendung, die für die die Anzahl von aktiven Objekten ungleich NULL ist – das Framework Blendet Sie aus der Anwendung aus Sicht des Benutzers, vollständig heruntergefahren. Die `AfxOleCanExitApp` -Funktion zeigt an, ob die Anwendung beendet werden kann.

Rufen Sie `AfxOleLockApp` aller Objekte, die OLE-Schnittstellen verfügbar macht, wenn es nicht wünschenswert, dass das Objekt zerstört werden, während noch von einer Clientanwendung verwendet werden sollen. Rufen Sie außerdem `AfxOleUnlockApp` im Destruktor der jedes Objekt, das Aufrufe `AfxOleLockApp` im Konstruktor. In der Standardeinstellung `COleDocument` (und abgeleitete Klassen) automatisch sperren und entsperren Sie die Anwendung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  AfxOleUnlockApp

Verringert die Framework Anzahl von aktiven Objekten in der Anwendung.

```
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter `AfxOleLockApp` für Weitere Informationen zu erhalten.

Wenn die Anzahl von aktiven Objekten NULL ist, erreicht `AfxOleOnReleaseAllObjects` aufgerufen wird.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [AfxOleLockApp](#afxolelockapp).

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

Die Klassenfactory des angegebenen Steuerelements sperrt, sodass dynamisch erstellte, mit dem Steuerelement verknüpfte Daten im Arbeitsspeicher beizubehalten.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Die eindeutige Klasse-ID des Steuerelements.

*lpszProgID*<br/>
Die eindeutige Programm-ID des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Klassenfactory des Steuerelements erfolgreich gesperrt wurde, andernfalls 0.

### <a name="remarks"></a>Hinweise

Dies kann die Anzeige der Steuerelemente erheblich beschleunigen. Z. B. einmal Sie ein Steuerelement in einem Dialogfeld erstellen und Sperren Sie das Steuerelement mit `AfxOleLockControl`, Sie müssen nicht zum Erstellen und es dann erneut beenden, jedes Mal, wenn das Dialogfeld angezeigt wird oder beschädigt wird. Wenn der Benutzer öffnet und ein Dialogfeld, wiederholt schließt, kann Ihre Steuerelemente sperren erheblich Leistung verbessern. Wenn Sie das Steuerelement löschen möchten, rufen Sie `AfxOleUnlockControl`.

### <a name="example"></a>Beispiel

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass

Diese Funktion können Sie Ihren Server in der OLE-systemregistrierung registrieren.

```
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,
    LPCTSTR lpszClassName,
    LPCTSTR lpszShortTypeName,
    LPCTSTR lpszLongTypeName,
    OLE_APPTYPE nAppType = OAT_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Referenz-ID des Servers OLE-Klasse.

*lpszClassName*<br/>
Zeiger auf eine Zeichenfolge, die den Klassennamen des Servers Objekte enthält.

*lpszShortTypeName*<br/>
Zeiger auf eine Zeichenfolge mit den kurzen Namen des Objekttyps des Servers, z. B. "Diagramm".

*lpszLongTypeName*<br/>
Zeiger auf eine Zeichenfolge, enthält den langen Namen des Objekttyps des Servers, z. B. "Microsoft Excel 5.0 Chart".

*nAppType*<br/>
Ein Wert, aus der OLE_APPTYPE-Enumeration, die den Typ des OLE-Anwendung angibt. Mögliche Werte sind die folgenden:

- OAT_INPLACE_SERVER-Server verfügt über vollständigen Benutzeroberfläche.

- OAT_SERVER-Server unterstützt nur einbetten.

- OAT_CONTAINER-Container unterstützt Links zu einbettungen.

- OAT_DISPATCH_OBJECT `IDispatch`-fähige Objekt.

*rglpszRegister*<br/>
Array von Zeigern auf Zeichenfolgen, die die Schlüssel und Werte in die systemregistrierung OLE hinzugefügt werden, wenn keine vorhandenen Werte für die Schlüssel nicht gefunden werden.

*rglpszOverwrite*<br/>
Array von Zeigern auf Zeichenfolgen, die die Schlüssel und Werte in die systemregistrierung OLE hinzugefügt werden, wenn es sich bei die Registrierung vorhandene Werte für den angegebenen Schlüssel enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Klasse-Server erfolgreich registriert wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die meisten Anwendungen können `COleTemplateServer::Register` Dokumenttypen der Anwendung zu registrieren. Wenn es sich bei Ihrer Anwendung in der systemregistrierung Format nicht das typische Muster passt, können Sie `AfxOleRegisterServerClass` mehr Kontrolle.

Die Registrierung besteht aus einem Satz von Schlüsseln und Werten. Die *RglpszRegister* und *RglpszOverwrite* Argumente sind Arrays von Zeigern auf Zeichenfolgen und jeweils bestehend aus einem Schlüssel und Wert voneinander getrennt durch ein **NULL** Zeichen ( `'\0'`). Die einzelnen Zeichenfolgen kann ersetzbare Parameter werden die Zeichenfolgen, deren Stellen markiert haben *%1* über *%5*.

Die Symbole werden wie folgt ausgefüllt:

|Symbol|Wert|
|------------|-----------|
|%1|Klassen Sie-ID, die als Zeichenfolge formatiert.|
|%2|Klassenname|
|%3|Pfad zur ausführbaren Datei|
|%4|Kurze Typnamen|
|%5|Vom Typ Long name|

### <a name="requirements"></a>Anforderungen

**Header**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu

Implementiert die Benutzeroberfläche für die *Typename* Objekt-Befehl.

```
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,
    CMenu* pMenu,
    UINT iMenuItem,
    UINT nIDVerbMin,
    UINT nIDVerbMax = 0,
    UINT nIDConvert = 0);
```

### <a name="parameters"></a>Parameter

*pClient*<br/>
Ein Zeiger auf das Client-OLE-Element.

*pMenu*<br/>
Ein Zeiger auf das Menüobjekt, das aktualisiert werden.

*iMenuItem*<br/>
Der Index des dem Menüelement, das aktualisiert werden.

*nIDVerbMin*<br/>
Die Befehls-ID, die das primäre Verb entspricht.

*nIDVerbMax*<br/>
Die Befehls-ID, die auf das letzte Verb entspricht.

*nIDConvert*<br/>
Die ID für das Menüelement konvertieren.

### <a name="remarks"></a>Hinweise

Wenn der Server nur ein primäres Verb erkennt, wird das Menüelement "Verb *Typename* Objekt" und die *nIDVerbMin* -Befehl gesendet wird, wenn der Benutzer den Befehl auswählt. Wenn der Server erkennt mehrere Verben, wird das Menüelement " *Typename* Objekt" und ein Untermenü mit alle Verben wird angezeigt, wenn der Benutzer den Befehl auswählt. Wenn der Benutzer ein Verb im Untermenü auswählt *nIDVerbMin* wird gesendet, wenn das erste Verb ausgewählt wird, *nIDVerbMin* + 1 wird gesendet, wenn das zweite Verb ausgewählt und So weiter. Der Standardwert `COleDocument` Implementierung kümmert sich dieses Feature.

Sie benötigen die folgende Anweisung im Ressourcenskript für Ihren Client-Anwendung (. RC)-Datei:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>Anforderungen

**Header**: afxole.h

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl

Entsperrt die Klassenfactory des angegebenen Steuerelements.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Die eindeutige Klasse-ID des Steuerelements.

*lpszProgID*<br/>
Die eindeutige Programm-ID des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Klassenfactory des Steuerelements erfolgreich entsperrt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein Steuerelement ist gesperrt, mit `AfxOleLockControl`, sodass Sie dynamisch erstellte mit dem Steuerelement verknüpfte Daten im Arbeitsspeicher beizubehalten. Dies kann die Darstellung des Steuerelements erheblich beschleunigt, da das Steuerelement muss nicht erstellt und zerstört wird jedes Mal, wenn er angezeigt wird. Wenn Sie das Steuerelement löschen möchten, rufen Sie `AfxOleUnlockControl`.

### <a name="example"></a>Beispiel

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
