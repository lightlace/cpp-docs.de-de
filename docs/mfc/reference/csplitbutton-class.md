---
title: CSplitButton-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: ca4899714fa336d058b2a53bcd5103c5b0c993e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547276"
---
# <a name="csplitbutton-class"></a>CSplitButton-Klasse

Die `CSplitButton` Klasse stellt einen SplitButton-Steuerelement dar. Das Steuerelement mit einer unterteilten Schaltfläche führt ein Standardverhalten aus, wenn ein Benutzer auf den Hauptteil der Schaltfläche klickt, und zeigt ein Dropdownmenü an, wenn ein Benutzer auf den Dropdownpfeil der Schaltfläche klickt.

## <a name="syntax"></a>Syntax

```
class CSplitButton : public CButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSplitButton::CSplitButton](#csplitbutton)|Erstellt ein `CSplitButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitButton::Create](#create)|Ein Trennschaltflächen-Steuerelement erstellt, mit der angegebenen Formate und hängt es an der aktuellen `CSplitButton` Objekt.|
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Legt fest, der Dropdown-Menü, das angezeigt wird, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitButton::OnDropDown](#ondropdown)|Verarbeitet die BCN_DROPDOWN-Benachrichtigungen, die das System sendet, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.|

## <a name="remarks"></a>Hinweise

Die `CSplitButton` abgeleitete Klasse wird die [CButton](../../mfc/reference/cbutton-class.md) Klasse. Das SplitButton-Steuerelement ist ein Schaltflächensteuerelement, dessen Stil BS_SPLITBUTTON ist. Ein benutzerdefiniertes Menü angezeigt, wenn ein Benutzer auf den Dropdown-Pfeil klickt. Weitere Informationen finden Sie auf die BS_SPLITBUTTON und BS_DEFSPLITBUTTON Formatvorlagen in [Button-Stile](/windows/desktop/Controls/button-styles).

Die folgende Abbildung zeigt ein Dialogfeld, das in einem Pagersteuerelement und einem (1) SplitButton-Steuerelement enthält. (2) Dropdown-Pfeil bereits geklickt wurde, und klicken Sie im Untermenü (3) wird angezeigt.

![Dialogfeld mit einer Trennschaltfläche und einem Pager-Steuerelement. ](../../mfc/reference/media/splitbutton_pager.png "Splitbutton_pager")

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

Diese Klasse wird in Windows Vista und höheren Versionen unterstützt.

Zusätzliche Anforderungen für diese Klasse werden in beschrieben [erstellen Anforderungen für Windows Vista-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md).

##  <a name="create"></a>  CSplitButton::Create

Ein Trennschaltflächen-Steuerelement erstellt, mit der angegebenen Formate und hängt es an der aktuellen `CSplitButton` Objekt.

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
|*dwStyle*|[in] Eine bitweise Kombination (OR) von Formatvorlagen, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Button-Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).|
|*Rect*|[in] Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|
|*pParentWnd*|[in] Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|
|*nID*|[in] Die ID des Steuerelements.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton

Erstellt ein `CSplitButton`-Objekt. Geben Sie die Parameter des Konstruktors ein Untermenü, das angezeigt wird, wenn ein Benutzer auf die Dropdown-Pfeil, der das SplitButton-Steuerelement klickt.

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
|*nMenuId*|[in] Die Ressourcen-ID der Menüleiste.|
|*nSubMenuId*|[in] Die Ressourcen-ID eines Untermenüs darstellt.|
|*pMenu*|[in] Ein Zeiger auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt, das ein Untermenü angibt. Die `CSplitButton` Objekt löscht die `CMenu` -Objekt und seine zugehörigen HMENU bei der `CSplitButton` Objekt den Gültigkeitsbereich verlässt.|

### <a name="remarks"></a>Hinweise

Verwenden der [CSplitButton::Create](#create) Methode erstellen ein Trennschaltflächen-Steuerelement, und fügen Sie ihn auf die `CSplitButton` Objekt.

##  <a name="ondropdown"></a>  CSplitButton::OnDropDown

Verarbeitet die BCN_DROPDOWN-Benachrichtigungen, die das System sendet, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pNMHDR*|[in] Zeiger auf ein [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) -Struktur, die Informationen der [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown) Benachrichtigung.|
|*pResult*|[out] (Nicht verwendet; es wird kein Wert zurückgegeben.) Rückgabewert von der [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown) Benachrichtigung.|

### <a name="remarks"></a>Hinweise

Klickt der Benutzer auf die Dropdown-Pfeil auf einem SplitButton-Steuerelement, System eine BCN_DROPDOWN-Benachrichtigung sendet Nachrichten, die die `OnDropDown` verarbeitet. Allerdings die `CSplitButton` Objekt nicht weiter die BCN_DROPDOWN-Benachrichtigung, um das Steuerelement, das SplitButton-Steuerelement enthält. Daher kann nicht das enthaltende Steuerelement eine benutzerdefinierte Aktion als Reaktion auf die Benachrichtigung nicht unterstützt.

Verwenden Sie zum Implementieren einer benutzerdefinierten Aktion, die das enthaltende Steuerelement unterstützt einen [CButton](../../mfc/reference/cbutton-class.md) Objekt mit dem Format BS_SPLITBUTTON anstelle von einem `CSplitButton` Objekt. Implementieren Sie dann einen Handler für die BCN_DROPDOWN-Benachrichtigung in der `CButton` Objekt. Weitere Informationen finden Sie unter [Button-Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).

Verwenden Sie zum Implementieren einer benutzerdefinierten Aktion, die unterteilte Schaltfläche selbst unterstützt steuern [Nachricht Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md). Leiten Sie eine eigene Klasse von der `CSplitButton` Klasse und nennen Sie ihn z. B. CMySplitButton. Fügen Sie die folgenden meldungszuordnung klicken Sie dann auf Ihre Anwendung die BCN_DROPDOWN-Benachrichtigung zu verarbeiten:

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu

Legt fest, der Dropdown-Menü, das angezeigt wird, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.

```
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nMenuId*|[in] Die Ressourcen-ID der Menüleiste.|
|*nSubMenuId*|[in] Die Ressourcen-ID eines Untermenüs darstellt.|
|*pMenu*|[in] Zeiger auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt, das ein Untermenü angibt. Die `CSplitButton` Objekt löscht die `CMenu` -Objekt und seine zugehörigen HMENU bei der `CSplitButton` Objekt den Gültigkeitsbereich verlässt.|

### <a name="remarks"></a>Hinweise

Die *nMenuId* Parameter identifiziert eine Menüleiste, das eine horizontale Liste von Menüleistenelementen ist. Die *nSubMenuId* -Parameter ist eine nullbasierte Indexnummer, die ein Untermenü, erfahren Sie, welche die Dropdown-Liste von Menüelementen, die jede Menüleistenelement zugeordnet ist. Eine typische Anwendung enthält beispielsweise ein Menü mit den Menüleistenelementen "File", "Bearbeiten" und "Help". Die "Datei" Menüleistenelement verfügt über ein Untermenü, das die Menüelemente enthält "Öffnen", "Schließen" und "Exit". Wenn der Dropdown-Pfeil des unterteilte Schaltfläche des Steuerelements geklickt wird, zeigt das Steuerelement im angegebene Untermenü, nicht in der Menüleiste aus.

Die folgende Abbildung zeigt ein Dialogfeld, das in einem Pagersteuerelement und einem (1) SplitButton-Steuerelement enthält. (2) Dropdown-Pfeil bereits geklickt wurde, und klicken Sie im Untermenü (3) wird angezeigt.

![Dialogfeld mit einer Trennschaltfläche und einem Pager-Steuerelement. ](../../mfc/reference/media/splitbutton_pager.png "Splitbutton_pager")

### <a name="example"></a>Beispiel

Die erste Anweisung in das folgende Codebeispiel veranschaulicht die [CSplitButton::SetDropDownMenu](#setdropdownmenu) Methode. Wir erstellt im Menü mit den Visual Studio-Ressourcen-Editor, der die Menü-Balken-ID, IDR_MENU1 automatisch benannt. Die *nSubMenuId* -Parameter, der 0 (null) ist, bezieht sich auf das einzige Untermenü der Menüleiste.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[CSplitButton-Klasse](../../mfc/reference/csplitbutton-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)
