---
title: CMDITabInfo-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
ms.openlocfilehash: a42128d097c9d63d82243090e2e215a250ff432b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341691"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo-Klasse

Die `CMDITabInfo` Klasse wird verwendet, um zum Übergeben von Parametern [CMDIFrameWndEx:: Enablemditabbedgroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) Methode. Legen Sie Member dieser Klasse fest, um das Verhalten der MDI-Gruppen im Registerkartenformat zu steuern.

## <a name="syntax"></a>Syntax

```
class CMDITabInfo
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|Standardkonstruktor|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMDITabInfo::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Gibt an, ob eine **schließen** Schaltfläche auf die Bezeichnung der aktiven Registerkarte angezeigt wird.|
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Gibt an, ob der MDI-Registerkarten Farbe.|
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Gibt an, ob die Gruppe von Registerkarten ein Popupmenü angezeigt, die zeigt eine Liste der geöffneten Dokumente oder scrollschaltflächen angezeigt.|
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Gibt an, ob der Benutzer die Positionen der Tabstopps durch Ziehen von austauschen kann.|
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Gibt an, ob Registerkarten einen flachen Frame haben.|
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Gibt an, ob jede registerkartenbezeichnung zeigt eine **schließen** Schaltfläche.|
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Gibt an, ob benutzerdefinierte QuickInfos aktiviert sind.|
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Gibt an, ob Symbole auf MDI-Registerkarten angezeigt werden soll.|
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Gibt an, die Rahmengröße der einzelnen Registerkartenfenster.|
|[CMDITabInfo::m_style](#m_style)|Gibt die Art der registerkartenbezeichnungen.|
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Gibt an, ob die Bezeichnungen für die Registerkarten am oberen oder unteren Rand der Seite befinden.|

## <a name="remarks"></a>Hinweise

Diese Klasse gibt die Parameter der MDI-Registerkartengruppen, die das Framework erstellt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Festlegen der Werte, der die verschiedenen Membervariablen in `CMDITabInfo` Klasse.

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxmdiclientareawnd.h

##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton;

Gibt an, ob eine **schließen** Schaltfläche auf die Bezeichnung der aktiven Registerkarte angezeigt wird.

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>Hinweise

Bei "true", zeigt die Bezeichnung der aktiven Registerkarte ein **schließen** Schaltfläche. Die **schließen** Schaltfläche wird von der rechten oberen Ecke des Registerkartenbereichs entfernt. Andernfalls wird die Bezeichnung der aktiven Registerkarte nicht angezeigt ein **schließen** Schaltfläche. Die **schließen** Schaltfläche in der oberen rechten Ecke des Registerkartenbereichs angezeigt.

##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor

Gibt an, ob jede MDI-Registerkarte mit eine eigenen Farbe hat.

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>Hinweise

Bei "true", hat jede Registerkarte eine eigenen Farbe. Der Satz von Farben wird von der MFC-Bibliothek verwaltet. Andernfalls werden die Registerkarten in Weiß angezeigt. Der Standardwert ist "false".

##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu

Gibt an, ob jede Registerkarte ein Popupmenü angezeigt, die eine Liste der geöffneten Dokumente am rechten Rand des Registerkartenbereichs angezeigt wird.

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>Hinweise

Bei "true", jede Registerkarte Windows zeigt ein Popupmenü an, die eine Liste der geöffneten Dokumente am rechten Rand des Registerkartenbereichs angezeigt wird; Andernfalls zeigt das Registerkartenfenster scrollschaltflächen am rechten Rand des Registerkartenbereichs. Der Standardwert ist "false".

##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap

Gibt an, ob der Benutzer die Positionen der Tabstopps durch Ziehen von austauschen kann.

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>Hinweise

Bei "true", kann der Benutzer auf die Positionen der Tabstopps durch Ziehen ändern. Andernfalls kann nicht der Benutzer die Positionen der Tabstopps ändern. Der Standardwert ist "true".

##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame

Gibt an, ob jede Registerkartenfenster einen flachen Rahmen besitzt.

```
BOOL m_bFlatFrame;
```

##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton

Gibt an, ob jedes Registerkartenfenster zeigt ein **schließen** Schaltfläche.

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>Hinweise

Bei "true", jedes Registerkartenfenster zeigt die **schließen** Schaltfläche am rechten Rand der Registerkarte. Andernfalls die **schließen** Schaltfläche nicht angezeigt. Der Standardwert ist "true".

##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips

Gibt an, ob QuickInfos für Registerkarten.

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>Hinweise

True gibt an, sendet die Anwendung eine Nachricht AFX_WM_ON_GET_TAB_TOOLTIP zum Hauptframe auf. Sie können diese Meldung verarbeiten, mithilfe der ON_REGISTERED_MESSAGE-Makro.

##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons

Gibt an, ob Symbole auf MDI-Registerkarten angezeigt werden soll.

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>Hinweise

Bei "true", werden die Symbole auf den einzelnen MDI-Registerkarten angezeigt. Andernfalls werden die Symbole nicht auf Registerkarten angezeigt. Der Standardwert ist "false".

##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize

Die Rahmengröße angibt in Pixel der einzelnen Registerkartenfenster.

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>Hinweise

[CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) gibt den Standardwert zurück.

##  <a name="m_style"></a>  CMDITabInfo::m_style

Gibt die Art der registerkartenbezeichnungen.

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>Hinweise

Geben Sie eine der folgenden Formate für die registerkartenbezeichnungen:

|||
|-|-|
|STYLE_3D|3D-Stil.  |
|STYLE_3D_ONENOTE|Microsoft OneNote-Format.  |
|STYLE_3D_VS2005|Microsoft Visual Studio 2005-Format.  |
|STYLE_3D_SCROLLED|3D-Stil mit registerkartenbezeichnungen Rechteck.  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|Flache mit gemeinsamen horizontalen Bildlaufleiste.  |
|STYLE_3D_ROUNDED_SCROLL|3D-Stil mit round registerkartenbezeichnungen.  |

##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation

Gibt an, ob die Bezeichnungen für die Registerkarten am oberen oder unteren Rand der Seite befinden.

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>Hinweise

Gelten Sie für die Registerkarten eine der folgenden Speicherort Flags:

- LOCATION_BOTTOM: die Bezeichnungen der Registerkarten befinden sich am unteren Rand der Seite.

- LOCATION_TOP: die Bezeichnungen für die Registerkarten am oberen Rand der Seite gespeichert sind

##  <a name="serialize"></a>  CMDITabInfo::Serialize

Liest oder schreibt dieses Objekt aus einem Archiv oder in ein Archiv.

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
[in] Ein [CArchive-Klasse](../../mfc/reference/carchive-class.md) zu serialisierende Objekt.

## <a name="see-also"></a>Siehe auch

[CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI-Gruppen im Registerkartenformat](../../mfc/mdi-tabbed-groups.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
