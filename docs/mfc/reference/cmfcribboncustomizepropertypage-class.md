---
title: CMFCRibbonCustomizePropertyPage-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 8c790ca249f34a3c9b36d1bd77dafdc4a91bd352
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288908"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage-Klasse

Implementiert eine benutzerdefinierte Seite für die **anpassen** Dialogfeld in Menüband-basierten Anwendungen.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Erstellt ein `CMFCRibbonCustomizePropertyPage`-Objekt.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Fügt eine benutzerdefinierte Kategorie, um die **Befehle** im Kombinationsfeld.|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Vom System aufgerufen wird, wenn ein Benutzer klickt **OK** auf die **anpassen** Dialogfeld.|

## <a name="remarks"></a>Hinweise

Sollten Sie benutzerdefinierte Befehle hinzufügen, um die **anpassen** (Dialogfeld), müssen Sie die Nachricht AFX_WM_ON_RIBBON_CUSTOMIZE behandeln. Instanziieren Sie in der Message-Handler, ein `CMFCRibbonCustomizePropertyPage` Objekt im Stapel. Erstellen Sie eine Liste mit benutzerdefinierten Befehlen, und klicken Sie dann rufen `AddCustomCategory` die neue Seite hinzufügen der **anpassen** Dialogfeld.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonCustomizePropertyPage` Objekt und eine benutzerdefinierte Kategorie hinzufügen.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribboncustomizedialog.h

##  <a name="addcustomcategory"></a>  CMFCRibbonCustomizePropertyPage::AddCustomCategory

Fügt eine benutzerdefinierte Kategorie, um die **Befehle** im Kombinationsfeld.

```
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*Wert*|[in] Gibt den Namen der benutzerdefinierten Kategorie an.|
|*lstIDS*|[in] Enthält die Multifunktionsleiste Befehls-IDs in der benutzerdefinierten Kategorie angezeigt werden.|

### <a name="remarks"></a>Hinweise

Diese Methode fügt eine Kategorie mit dem Namen *Wert* auf die **Befehle** im Kombinationsfeld. Wenn der Benutzer die Kategorie auswählt, werden die Befehle in angegebenen *LstIDS* angezeigt werden, in der Befehlsliste.

##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

Erstellt ein `CMFCRibbonCustomizePropertyPage`-Objekt.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Parameter

*pRibbonBar*<br/>
[in] Ein Zeiger auf ein Menüband-Steuerelement für die die Optionen zum Anpassen.

##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK

Calleld durch das System, wenn ein Benutzer klickt **OK** auf die **anpassen** Dialogfeld.

```
virtual void OnOK();
```

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung gilt, die im ausgewählten Optionen der **anpassen** im Dialogfeld auf der Symbolleiste für den Schnellzugriff.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
