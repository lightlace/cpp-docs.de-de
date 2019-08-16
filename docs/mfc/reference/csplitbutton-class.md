---
title: CSplitButton-Klasse
ms.date: 11/19/2018
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
ms.openlocfilehash: a552334adb4963f45388a798eb0723e61c09ec85
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502838"
---
# <a name="csplitbutton-class"></a>CSplitButton-Klasse

Die `CSplitButton` -Klasse stellt ein Steuerelement für unterteilte Schaltflächen Das Steuerelement mit einer unterteilten Schaltfläche führt ein Standardverhalten aus, wenn ein Benutzer auf den Hauptteil der Schaltfläche klickt, und zeigt ein Dropdownmenü an, wenn ein Benutzer auf den Dropdownpfeil der Schaltfläche klickt.

## <a name="syntax"></a>Syntax

```
class CSplitButton : public CButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSplitButton:: CSplitButton](#csplitbutton)|Erstellt ein `CSplitButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitButton:: Create](#create)|Erstellt ein Steuerelement für eine unterteilte Schaltfläche mit angegebenen Stilen und `CSplitButton` fügt es an das aktuelle-Objekt an.|
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Legt das Dropdown Menü fest, das angezeigt wird, wenn ein Benutzer auf den Dropdown Pfeil des aktuellen Steuer Elements für eine unterteilte Schaltfläche klickt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitButton::OnDropDown](#ondropdown)|Verarbeitet die BCN_DROPDOWN-Benachrichtigung, die vom System gesendet wird, wenn ein Benutzer auf den Dropdown Pfeil des aktuellen Steuer Elements für eine unterteilte Schaltfläche klickt.|

## <a name="remarks"></a>Hinweise

Die `CSplitButton` -Klasse wird von der [CButton](../../mfc/reference/cbutton-class.md) -Klasse abgeleitet. Das Steuerelement für die unterteilte Schaltfläche ist ein Schaltflächen-Steuerelement, dessen Format Wenn ein Benutzer auf den Dropdown Pfeil klickt, wird ein benutzerdefiniertes Menü angezeigt. Weitere Informationen finden Sie unter den Stilen BS_SPLITBUTTON und BS_DEFSPLITBUTTON in [Schalt](/windows/win32/Controls/button-styles)Flächen Formaten.

In der folgenden Abbildung wird ein Dialogfeld dargestellt, das ein Pager-Steuerelement und ein (1) Split Button-Steuerelement enthält. Auf den (2) Dropdown Pfeil wurde bereits geklickt, und das Untermenü (3) wird angezeigt.

![Dialog mit einem SplitButton-und Pager-Steuerelement.](../../mfc/reference/media/splitbutton_pager.png "Dialog mit einem SplitButton-und Pager-Steuerelement.")

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

Diese Klasse wird in Windows Vista und höher unterstützt.

Weitere Anforderungen für diese Klasse werden unter Buildanforderungen [für allgemeine Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md)-Steuerelemente beschrieben.

##  <a name="create"></a>CSplitButton:: Create

Erstellt ein Steuerelement für eine unterteilte Schaltfläche mit angegebenen Stilen und `CSplitButton` fügt es an das aktuelle-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwStyle*|in Eine bitweise Kombination (or) der Stile, die auf das-Steuerelement angewendet werden sollen. Weitere Informationen finden Sie unter [Schaltflächen Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).|
|*Rect*|in Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position und Größe des Steuer Elements enthält.|
|*pParentWnd*|in Ein nicht-NULL-Zeiger auf ein [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuer Elements ist.|
|*nID*|in Die ID des Steuer Elements.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

##  <a name="csplitbutton"></a>CSplitButton:: CSplitButton

Erstellt ein `CSplitButton`-Objekt. Die Parameter des Konstruktors geben ein Untermenü an, das angezeigt wird, wenn ein Benutzer auf den Dropdown Pfeil des Steuer Elements für die unterteilte Schaltfläche klickt.

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nMenuId*|in Die Ressourcen-ID der Menüleiste.|
|*nSubMenuId*|in Die Ressourcen-ID eines Untermenüs.|
|*pMenu*|in Ein Zeiger auf ein [CMenu](../../mfc/reference/cmenu-class.md) -Objekt, das ein Untermenü angibt. Das- `CSplitButton` Objekt löscht `CMenu` das-Objekt und das zugehörige HMENU, wenn das Objekt den Gültigkeitsbereich verlässt. `CSplitButton`|

### <a name="remarks"></a>Hinweise

Verwenden Sie die [CSplitButton:: Create](#create) -Methode, um ein Steuerelement unterteilte Schaltflächen `CSplitButton` zu erstellen und an das-Objekt anzufügen.

##  <a name="ondropdown"></a>CSplitButton:: OnDropDown

Verarbeitet die BCN_DROPDOWN-Benachrichtigung, die vom System gesendet wird, wenn ein Benutzer auf den Dropdown Pfeil des aktuellen Steuer Elements für eine unterteilte Schaltfläche klickt.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pNMHDR*|in Zeiger auf eine [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) -Struktur, die Informationen über die [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) -Benachrichtigung enthält.|
|*pResult*|vorgenommen (Wird nicht verwendet. es wird kein Wert zurückgegeben.) Rückgabewert der [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) -Benachrichtigung.|

### <a name="remarks"></a>Hinweise

Wenn der Benutzer auf den Dropdown Pfeil auf einem Trenn Schaltfläche-Steuerelement klickt, sendet das System eine BCN_DROPDOWN `OnDropDown` -Benachrichtigungs Meldung, die von der Methode verarbeitet wird. `CSplitButton` Allerdings wird die BCN_DROPDOWN-Benachrichtigung nicht an das Steuerelement weiterleiten, das das Steuerelement für die unterteilte Schaltfläche enthält. Folglich kann das enthaltende Steuerelement eine benutzerdefinierte Aktion nicht als Antwort auf die Benachrichtigung unterstützen.

Um eine benutzerdefinierte Aktion zu implementieren, die das enthaltende Steuerelement unterstützt, verwenden Sie ein [CButton](../../mfc/reference/cbutton-class.md) -Objekt `CSplitButton` mit einem Stil von BS_SPLITBUTTON anstelle eines-Objekts. Implementieren Sie dann einen Handler für die BCN_DROPDOWN-Benachrichtigung `CButton` im-Objekt. Weitere Informationen finden Sie unter [Schaltflächen Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).

Verwenden Sie [Nachrichten Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md), um eine benutzerdefinierte Aktion zu implementieren, die das Steuerelement für die unterteilte Schaltfläche Leiten Sie eine eigene Klasse von `CSplitButton` der-Klasse ab, und benennen Sie Sie, z. b. cmysplitbutton. Fügen Sie der Anwendung dann die folgende Meldungs Zuordnung hinzu, um die BCN_DROPDOWN-Benachrichtigung zu behandeln:

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

##  <a name="setdropdownmenu"></a>CSplitButton:: setdropdownmenu

Legt das Dropdown Menü fest, das angezeigt wird, wenn ein Benutzer auf den Dropdown Pfeil des aktuellen Steuer Elements für eine unterteilte Schaltfläche klickt.

```
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nMenuId*|in Die Ressourcen-ID der Menüleiste.|
|*nSubMenuId*|in Die Ressourcen-ID eines Untermenüs.|
|*pMenu*|in Ein Zeiger auf ein [CMenu](../../mfc/reference/cmenu-class.md) -Objekt, das ein Untermenü angibt. Das- `CSplitButton` Objekt löscht `CMenu` das-Objekt und das zugehörige HMENU, wenn das Objekt den Gültigkeitsbereich verlässt. `CSplitButton`|

### <a name="remarks"></a>Hinweise

Der *nmenuid* -Parameter identifiziert eine Menüleiste, bei der es sich um eine horizontale Liste von Menüleisten Elementen handelt. Der *nsubmenuid* -Parameter ist eine Null basierte Indexnummer, die ein Untermenü identifiziert. Dies ist die Dropdown Liste mit Menü Elementen, die jedem Menüleisten Element zugeordnet sind. Beispielsweise verfügt eine typische Anwendung über ein Menü, das die Menüleisten Elemente, "file", "Edit" und "Help" enthält. Das Menüleisten Element "Datei" enthält ein Untermenü mit den Menü Elementen "Öffnen", "Schließen" und "beenden". Wenn Sie auf den Dropdown Pfeil des Trenn Schaltflächen-Steuer Elements klicken, zeigt das-Steuerelement das angegebene Untermenü an, nicht die Menüleiste.

In der folgenden Abbildung wird ein Dialogfeld dargestellt, das ein Pager-Steuerelement und ein (1) Split Button-Steuerelement enthält. Auf den (2) Dropdown Pfeil wurde bereits geklickt, und das Untermenü (3) wird angezeigt.

![Dialog mit einem SplitButton-und Pager-Steuerelement.](../../mfc/reference/media/splitbutton_pager.png "Dialog mit einem SplitButton-und Pager-Steuerelement.")

### <a name="example"></a>Beispiel

Die erste Anweisung im folgenden Codebeispiel veranschaulicht die [CSplitButton:: setdropdownmenu](#setdropdownmenu) -Methode. Wir haben das Menü mit dem Ressourcen-Editor von Visual Studio erstellt, der automatisch die Menüleisten-ID "IDR_MENU1" trägt. Der *nsubmenuid* -Parameter, der 0 (null) ist, verweist auf das einzige Untermenü der Menüleiste.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[CSplitButton-Klasse](../../mfc/reference/csplitbutton-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)
