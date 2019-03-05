---
title: CMFCRibbonMainPanel-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: e4bd1ab8cffc87d5079518cf9a1d6e430ca40fd9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294443"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel-Klasse

Implementiert einen Menübandbereich, der anzeigt, wenn Sie auf die [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).

## <a name="syntax"></a>Syntax

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Standardkonstruktor|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonMainPanel::Add](#add)|Fügt ein Menübandelement auf den linken Bereich von der Anwendung Schaltflächenbereich hinzu. (Überschreibt [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Fügt eine Zeichenfolge, die zuletzt verwendete Dateien Listenmenü hinzu.|
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Ein Menübandelement und unteren Bereich der Anwendung Menübandbereich hinzugefügt.|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Fügt ein Menübandelement in den rechten Bereich von der Anwendung Schaltflächenbereich hinzu.|
|`CMFCRibbonMainPanel::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Gibt ein Rechteck, das den Bereich der Hauptbereich Menüband darstellt.|
|`CMFCRibbonMainPanel::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Zeigt das Framework die `CMFCRibbonMainPanel` beim Öffnen des Anwendung-Bereichs. Es enthält drei Bereiche:

- Der linke Bereich enthält Dateien, z. B. zugeordneten Befehle **öffnen**, **speichern**, **Drucken**, und **schließen**. Um einen Befehl in diesen Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::Add](#add).

- Der rechte Bereich enthält Optionen, die den Befehl ändern, den Sie im linken Bereich klicken. Angenommen, Sie klicken **speichern** im rechte Bereich kann im linken Bereich verfügbaren Dateitypen anzeigen. Um ein Element in diesen Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToRight](#addtoright).

- Im unteren Bereich enthält die Schaltflächen, mit denen Sie so ändern Sie die Einstellungen der Anwendung und das Programm zu beenden. Um ein Element in diesen Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToBottom](#addtobottom).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonMainPanel.h

##  <a name="add"></a>  CMFCRibbonMainPanel::Add

Fügt ein Menübandelement auf den linken Bereich von der Anwendung Schaltflächenbereich hinzu.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Parameter

*pElem*<br/>
[in, out] Ein Zeiger auf das Menübandelement den Hauptbereich hinzu.

### <a name="remarks"></a>Hinweise

Der Bereich wird ein Menübandelement hinzugefügt. Mit dieser Methode hinzugefügte Elemente werden in der linken Spalte der Hauptbereich befinden.

##  <a name="addrecentfileslist"></a>  CMFCRibbonMainPanel::AddRecentFilesList

Fügt eine Zeichenfolge, die zuletzt verwendete Dateien Listenmenü hinzu.

```
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
Gibt die Zeichenfolge, die Liste der zuletzt geöffneten Dateien hinzugefügt.

*nWidth*<br/>
Gibt die Breite in Pixel der aktuellen Dateibereich an.

### <a name="remarks"></a>Hinweise

##  <a name="addtobottom"></a>  CMFCRibbonMainPanel::AddToBottom

Ein Menübandelement und unteren Bereich der Anwendung Menübandbereich hinzugefügt.

```
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Parameter

*pElem*<br/>
[in, out] Ein Zeiger auf das Menübandelement, an das Ende der Hauptbereich hinzugefügt.

### <a name="remarks"></a>Hinweise

##  <a name="addtoright"></a>  CMFCRibbonMainPanel::AddToRight

Fügt ein Menübandelement in den rechten Bereich von der Anwendung Schaltflächenbereich hinzu.

```
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Parameter

*pElem*<br/>
Ein Zeiger auf ein Menübandelement rechts neben den Hauptbereich hinzugefügt werden.

*nWidth*<br/>
Gibt die Breite in Pixel im rechten Bereich an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion im rechten Bereich ein Menübandelement hinzu. Im rechte Bereich in der Regel zeigt die Dateiliste der zuletzt geöffneten, aber Sie können eine beliebige andere Menübandelement hier hinzufügen.

##  <a name="getcommandsframe"></a>  CMFCRibbonMainPanel::GetCommandsFrame

Gibt ein Rechteck, das den Bereich der Hauptbereich Menüband darstellt.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Rechteck, das den Bereich der Hauptbereich Menüband darstellt.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel-Klasse](../../mfc/reference/cmfcribbonpanel-class.md)
