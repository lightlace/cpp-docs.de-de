---
title: CCmdUI-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
ms.openlocfilehash: 12d9ead736a84d89b04f7b68ed76da8ccea22d0c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302870"
---
# <a name="ccmdui-class"></a>CCmdUI-Klasse

Wird verwendet, nur innerhalb einer `ON_UPDATE_COMMAND_UI` Ereignishandler in einer `CCmdTarget`-abgeleitete Klasse.

## <a name="syntax"></a>Syntax

```
class CCmdUI
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCmdUI::ContinueRouting](#continuerouting)|Teilt den Befehlsrouting Mechanismus weiterhin Weiterleitung der aktuellen Nachricht der Vererbungskette von Handlern.|
|[CCmdUI::Enable](#enable)|Aktiviert oder deaktiviert das Benutzeroberflächen-Element für diesen Befehl.|
|[CCmdUI::SetCheck](#setcheck)|Legt den Aktivierungszustand des Elements Benutzeroberfläche für diesen Befehl fest.|
|[CCmdUI::SetRadio](#setradio)|Wie die `SetCheck` Memberfunktion kann jedoch Optionsfeldgruppen.|
|[CCmdUI::SetText](#settext)|Legt den Text für das Element der Benutzeroberfläche für diesen Befehl.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CCmdUI::m_nID](#m_nid)|Die ID des Benutzeroberflächen-Objekts.|
|[CCmdUI::m_nIndex](#m_nindex)|Der Index des Benutzeroberflächen-Objekts.|
|[CCmdUI::m_pMenu](#m_pmenu)|Verweist auf das Menü, dargestellt durch die `CCmdUI` Objekt.|
|[CCmdUI::m_pOther](#m_pother)|Verweist auf das Fensterobjekt, das die Benachrichtigung gesendet.|
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Verweist auf die enthaltenen Untermenü dargestellt durch die `CCmdUI` Objekt.|

## <a name="remarks"></a>Hinweise

`CCmdUI` eine Basisklasse keinen.

Wenn ein Benutzer Ihrer Anwendung überträgt ein Menü, jede Menü Element muss wissen, ob es als aktiviert angezeigt werden sollen oder deaktiviert. Das Ziel eines Menübefehls stellt diese Informationen bereit, durch die Implementierung eines ON_UPDATE_COMMAND_UI-Handlers. Verwenden Sie für jeden Befehl Benutzeroberflächen-Objekte in Ihrer Anwendung die Fenster "Eigenschaften", um eine meldungszuordnung Eintrag und die Funktion der Prototyp für jeden Handler zu erstellen.

Wenn Sie im Menü heruntergeladen wird, das Framework sucht nach und ruft jede ON_UPDATE_COMMAND_UI-Handler ist, werden Aufrufe von jeder Handler `CCmdUI` Memberfunktionen wie `Enable` und `Check`, und das Framework zeigt dann entsprechend jedes Menüelement.

Ein Menüelement kann durch eine Steuerleiste Schaltfläche oder ein anderes Objekt der Befehl-Benutzeroberfläche ersetzt werden, ohne den Code innerhalb der `ON_UPDATE_COMMAND_UI` Handler.

In der folgende Tabelle werden die Auswirkungen zusammengefasst `CCmdUI`der Memberfunktionen, die auf verschiedene Befehls-UI-Elemente haben.

|Benutzeroberflächen-Element|Aktivieren|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|Menüelement|Aktiviert oder deaktiviert|Aktiviert oder deaktiviert|Überprüft, die mit einem Punkt|Legt Element text|
|Symbolleisten-Schaltfläche|Aktiviert oder deaktiviert|Auswählt, hebt die Auswahl, oder unbestimmten Zustand|Identisch mit `SetCheck`|(Nicht zutreffend)|
|Statusleiste|Wird der Text sichtbar oder unsichtbar|Legt Popout- oder ein normaler Rahmen|Identisch mit `SetCheck`|Legt Bereich – text|
|Normale Schaltfläche in `CDialogBar`|Aktiviert oder deaktiviert|Aktiviert oder deaktiviert das Kontrollkästchen|Identisch mit `SetCheck`|Legt Schaltfläche text|
|Im normalen-Steuerelement `CDialogBar`|Aktiviert oder deaktiviert|(Nicht zutreffend)|(Nicht zutreffend)|Legt Fenstertext|

Weitere Informationen zur Verwendung dieser Klasse finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CCmdUI`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="continuerouting"></a>  CCmdUI::ContinueRouting

Rufen Sie diese Memberfunktion zum Befehlsrouting Mechanismus zum Fortsetzen die aktuelle Nachricht der Vererbungskette von Handlern routing zu informieren.

```
void ContinueRouting();
```

### <a name="remarks"></a>Hinweise

Dies ist eine erweiterte Memberfunktion, die in Verbindung mit einer ON_COMMAND_EX-Handler verwendet werden soll, die FALSE zurückgibt. Weitere Informationen finden Sie unter [technischen Hinweis 6](../../mfc/tn006-message-maps.md).

##  <a name="enable"></a>  CCmdUI:: Enable auf

Rufen Sie diese Memberfunktion zum Aktivieren oder deaktivieren das Element der Benutzeroberfläche für diesen Befehl.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parameter

*bOn*<br/>
TRUE, wenn das Element "false" zu aktivieren, um ihn zu deaktivieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

##  <a name="m_nid"></a>  CCmdUI::m_nID

Die ID des Menüelements, Symbolleisten-Schaltfläche oder ein anderes Benutzeroberfläche-Objekt, das dargestellt durch die `CCmdUI` Objekt.

```
UINT m_nID;
```

##  <a name="m_nindex"></a>  CCmdUI::m_nIndex

Der Index des Menüelements, Symbolleisten-Schaltfläche oder ein anderes Benutzeroberfläche-Objekt, das dargestellt durch die `CCmdUI` Objekt.

```
UINT m_nIndex;
```

##  <a name="m_pmenu"></a>  CCmdUI::m_pMenu

Zeiger (der `CMenu` Typ), klicken Sie im Menü, dargestellt durch die `CCmdUI` Objekt.

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Hinweise

NULL, wenn das Element nicht um ein Menü befindet.

##  <a name="m_psubmenu"></a>  CCmdUI::m_pSubMenu

Zeiger (der `CMenu` Typ), enthalten im Untermenü durch dargestellt die `CCmdUI` Objekt.

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Hinweise

NULL, wenn das Element nicht um ein Menü befindet. Wenn das Sub-Menü ein Popupfenster wird *M_nID* enthält die ID des ersten Elements im Popup-Menü. Weitere Informationen finden Sie unter [technischen Hinweis 21](../../mfc/tn021-command-and-message-routing.md).

##  <a name="m_pother"></a>  CCmdUI::m_pOther

Zeiger (vom Typ `CWnd`) auf das Fensterobjekt, z. B. ein Tool oder der Statusleiste, die die Benachrichtigung gesendet.

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Hinweise

NULL, wenn das Element ein Menü oder einer nicht - `CWnd` Objekt.

##  <a name="setcheck"></a>  CCmdUI::SetCheck

Rufen Sie diese Memberfunktion, um das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Aktivierungszustand festgelegt.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>Parameter

*nCheck*<br/>
Gibt an, dessen Aktivierungszustand festgelegt. Wenn 0 (null) deaktiviert; Wenn 1, überprüft. und 2, legt fest, wenn unbestimmt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion funktioniert für Menüelemente und Symbolleisten-Schaltflächen. Unbestimmte Zustand gilt nur für Schaltflächen der Symbolleiste.

##  <a name="setradio"></a>  CCmdUI::SetRadio

Rufen Sie diese Memberfunktion, um das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Aktivierungszustand festgelegt.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parameter

*bOn*<br/>
True, um das Element zu aktivieren. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion funktioniert wie `SetCheck`, außer dass sie Elementen der Benutzeroberfläche, die Teil einer Optionsfeldgruppe verwendet. Deaktivieren die anderen Elemente in der Gruppe erfolgt nicht automatisch, es sei denn, die Elemente selbst die Optionsfeldgruppe Verhalten beibehalten.

##  <a name="settext"></a>  CCmdUI::SetText

Rufen Sie diese Memberfunktion um den Text des Benutzeroberflächen-Elements für diesen Befehl festzulegen.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Ein Zeiger auf eine Textzeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
