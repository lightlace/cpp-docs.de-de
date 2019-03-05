---
title: CDialogBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: 2ae7c941b527a7cbaa01bf43ef4d41c9a4975dac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302402"
---
# <a name="cdialogbar-class"></a>CDialogBar-Klasse

Stellt die Funktionalität eines nicht modalen Windows-Dialogfelds in einer Steuerleiste bereit.

## <a name="syntax"></a>Syntax

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDialogBar::CDialogBar](#cdialogbar)|Erstellt ein `CDialogBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDialogBar::Create](#create)|Erstellt eine Windows-Dialogleiste und fügt es der `CDialogBar` Objekt.|

## <a name="remarks"></a>Hinweise

Eine Dialogleiste ähnelt ein Dialogfeld, in der sie Windows-Standardsteuerelemente enthält, denen der Benutzer zwischen die TAB-Taste. Ähnlichkeit von einem anderen ist die Erstellung einer Dialogfeldvorlage, um die Dialogleiste darzustellen.

Erstellen und Verwenden einer Dialogleiste ähnelt erstellen und Verwenden einer `CFormView` Objekt. Verwenden Sie zunächst die [Dialog-Editor](../../windows/dialog-editor.md) einer Dialogfeldvorlage im Format WS_CHILD und kein anderer Stil definieren. Die Vorlage darf nicht das Format WS_VISIBLE sein. Rufen Sie in Ihrem Anwendungscode, den Konstruktor zum Erstellen der `CDialogBar` Objekt aus, und rufen Sie dann `Create` , erstellen Sie das Dialogleiste Fenster, und fügen Sie ihn auf die `CDialogBar` Objekt.

Weitere Informationen zu `CDialogBar`, finden Sie im Artikel [Dialogleisten](../../mfc/dialog-bars.md) und [technischer Hinweis 31](../../mfc/tn031-control-bars.md), Schiebeleisten-Steuerelemente.

> [!NOTE]
>  In der aktuellen Version einer `CDialogBar` Objekt kann keine Windows Forms-Steuerelemente hosten. Weitere Informationen zu Windows Forms-Steuerelementen in Visual C++, finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar

Erstellt ein `CDialogBar`-Objekt.

```
CDialogBar();
```

##  <a name="create"></a>  CDialogBar::Create

Lädt die Dialogfeld-Resource-Vorlage, die anhand des `lpszTemplateName` oder `nIDTemplate`, erstellt das Dialogleiste Fenster, legt den Stil und ordnet ihn dem `CDialogBar` Objekt.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element `CWnd` Objekt.

*lpszTemplateName*<br/>
Ein Zeiger auf den Namen der `CDialogBar` des Objekts im Dialogfeld Ressourcenvorlage.

*nStyle*<br/>
Der Stil für die Symbolleiste. Zusätzliche Toolbar-Stile, die unterstützt werden:

- CBRS_TOP Steuerleiste ist am oberen Rand des Fensters Frame.

- CBRS_BOTTOM Steuerleiste ist am unteren Rand der Frame-Fensters.

- CBRS_NOALIGN Steuerleiste ist nicht neu angeordnet, wenn das übergeordnete Element geändert wird.

- CBRS_TOOLTIPS-Steuerleiste werden QuickInfos angezeigt.

- CBRS_SIZE_DYNAMIC Steuerleiste ist dynamisch.

- CBRS_SIZE_FIXED Steuerleiste wurde behoben.

- CBRS_FLOATING Steuerleiste unverankert ist.

- CBRS_FLYBY-Statusleiste zeigt Informationen über die Schaltfläche.

- Steuerleiste CBRS_HIDE_INPLACE wird dem Benutzer nicht angezeigt.

*nID*<br/>
Die Steuerelement-ID, der die Dialogleiste werden soll.

*nIDTemplate*<br/>
Der Ressourcen-ID der `CDialogBar` Dialogfeldvorlage des Objekts.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Wenn Sie die Ausrichtungsart CBRS_TOP oder CBRS_BOTTOM angeben, die Dialogleiste Breite das Rahmenfenster ist und seine Höhe, die der Ressource angegeben werden ist, indem *nIDTemplate*. Wenn Sie die Ausrichtungsart CBRS_LEFT oder CBRS_RIGHT angeben, die Dialogleiste Höhe das Rahmenfenster ist und seine Breite, der vom angegebenen Ressource ist *nIDTemplate*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Muster CTRLBARS](../../visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFormView-Klasse](../../mfc/reference/cformview-class.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)
