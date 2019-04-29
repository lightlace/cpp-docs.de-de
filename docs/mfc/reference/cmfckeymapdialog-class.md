---
title: CMFCKeyMapDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: 65aa5ab0f24999ee23a97f383577b69584825502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388500"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog-Klasse

Die `CMFCKeyMapDialog` Klasse unterstützt ein Steuerelement, das Befehlen Tastaturtasten zuordnet.

## <a name="syntax"></a>Syntax

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Erstellt ein `CMFCKeyMapDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCKeyMapDialog::DoModal](#domodal)|Zeigt im Dialogfeld für die Zuordnung einer Tastatur an.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Wird aufgerufen, durch das Framework eine Zeichenfolge zu erstellen, die eine wichtige Zuordnung beschreibt. Standardmäßig enthält die Zeichenfolge an den Namen des Befehls, der Tastaturkombinationen und Beschreibung der Verknüpfung des Schlüssels.|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Ruft eine Zeichenfolge, die eine Liste mit Tastenkombinationen, die den angegebenen Befehl zugeordnet enthält.|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Wird vom Framework aufgerufen, bevor ein neues Element in das Steuerelement für die interne Liste eingefügt wird, die Karten-Steuerelement auf der Tastatur unterstützt.|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Wird aufgerufen, durch das Framework den Header für das Tastaturlayout auf einer neuen Seite zu drucken.|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Wird aufgerufen, durch das Framework eine tastaturelement für die Zuordnung zu drucken.|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Wird aufgerufen, durch das Framework Beschriftungen für die Spalten in der internen Steuerelement festlegen, die Karten-Steuerelement auf der Tastatur unterstützt.|
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Vom Framework aufgerufen, wenn ein Benutzer klickt der **Drucken** Schaltfläche.|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Wird aufgerufen, durch das Framework die Breite der Spalten in der internen Steuerelement festlegen, die Karten-Steuerelement auf der Tastatur unterstützt.|

## <a name="remarks"></a>Hinweise

Verwenden der `CMFCKeyMapDialog` Klasse, um ein Dialogfeld mit veränderbarer Größe Tastatur Zuordnung zu implementieren. Das Dialogfeld verwendet ein Listenansicht-Steuerelement zum Anzeigen von Tastenkombinationen in Visual Studio und die entsprechenden Befehle.

Verwenden der `CMFCKeyMapDialog` Klasse in einer Anwendung, übergeben eines Zeigers an das Hauptrahmenfenster als Parameter an die `CMFCKeyMapDialog` Konstruktor. Rufen Sie dann die `DoModal` Methode, um ein modales Dialogfeld starten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxkeymapdialog.h

##  <a name="cmfckeymapdialog"></a>  CMFCKeyMapDialog::CMFCKeyMapDialog

Erstellt ein `CMFCKeyMapDialog`-Objekt.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Parameter

*pWndParentFrame*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster der `CMFCKeyMapDialog` Objekt.

*bEnablePrint*<br/>
[in] True, wenn die Liste der Tastenkombinationen gedruckt werden kann. andernfalls "false". Der Standardwert ist "false".

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCKeyMapDialog` Klasse. In diesem Beispiel ist Teil der [Visual Studio-Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal

Zeigt im Dialogfeld für die Zuordnung einer Tastatur an.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Eine Ganzzahl mit Vorzeichen wie IDOK oder IDCANCEL, der an übergebene der [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) Methode. Die Methode wird wiederum das Dialogfeld geschlossen. Weitere Informationen finden Sie unter [Methode CDialog:: DoModal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Hinweise

Im Dialogfeld für die Zuordnung der Tastatur können Sie auswählen und Zuordnen von Tastenkombinationen auf verschiedene Kategorien von Befehlen. Darüber hinaus können Sie die ausgewählten Zugriffstasten und die entsprechenden Beschreibungen in die Zwischenablage kopieren.

##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem

Wird aufgerufen, durch das Framework eine Zeichenfolge zu erstellen, die eine wichtige Zuordnung beschreibt. Standardmäßig enthält die Zeichenfolge an den Namen des Befehls, der Tastaturkombinationen und Beschreibung der Verknüpfung des Schlüssels.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
[in] Der nullbasierte Index eines Elements in der internen Liste der wichtigsten Zuordnungen.

### <a name="return-value"></a>Rückgabewert

Ein `CString` Objekt, das den formatierten Text enthält.

### <a name="remarks"></a>Hinweise

##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys

Ruft einen Zeichenfolgenwert ab. Die Zeichenfolge enthält eine Liste mit Tastenkombinationen, die einen bestimmten Befehl zugeordnet sind.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Parameter

*uiCmdID*<br/>
[in] Eine Befehls-ID.

### <a name="return-value"></a>Rückgabewert

Eine durch Semikolons getrennt (';') Liste mit Tastenkombinationen, die den angegebenen Befehl zugeordnet ist.

### <a name="remarks"></a>Hinweise

##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem

Wird vom Framework aufgerufen, bevor ein neues Element in ein Steuerelement für die interne Liste eingefügt wird, die Karten-Steuerelement auf der Tastatur unterstützt.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Parameter

*pButton*<br/>
[in] Ein Zeiger auf eine Symbolleisten-Schaltfläche, die verwendet wird, um einen Befehlsnamen und eine Beschreibung eine Tastenkombination für den Schlüssel zuzuordnen. Das Key-Map-Element wird in einem Steuerelement für die interne Liste gespeichert.

*nItem*<br/>
[in] Ein nullbasierter Index, der angibt, wo der neue Schlüssel Map-Element im Listensteuerelement interne eingefügt.

### <a name="remarks"></a>Hinweise

##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader

Wird aufgerufen, durch das Framework den Header für das Tastaturlayout auf einer neuen Seite zu drucken.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Parameter

*dc*<br/>
[in] Der Gerätekontext für den Drucker.

*nPage*<br/>
[in] Die Seitenzahl der Seite gedruckt werden soll.

*cx*<br/>
[in] Der horizontale Offset des Headers, in Pixel.

### <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung die Höhe der gedruckten Text. Weitere Informationen finden Sie im Abschnitt Rückgabewert [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext).

### <a name="remarks"></a>Hinweise

Das Framework verwendet diese Methode so drucken Sie das Tastaturlayout. Standardmäßig gibt diese Methode, die Seitenzahl, Anwendungsname und Titel des Dateidialogfelds.

##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem

Wird aufgerufen, durch das Framework eine tastaturelement für die Zuordnung zu drucken.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Parameter

*dc*<br/>
[in] Der Gerätekontext des Druckers.

*nItem*<br/>
[in] Der nullbasierte Index des Elements, das gedruckt werden soll.

*y*<br/>
[in] Der vertikale Offset zwischen dem oberen Rand der Seite und die Position des Elements.

*cx*<br/>
[in] Der horizontale Offset zwischen dem linken Rand der Seite und die Position des Elements.

*bCalcHeight*<br/>
[in] True, um die optimale Höhe für das Drucken-Element zu berechnen. FALSE, wenn das Element Drucken abgeschnitten, damit er den Standardzwischenraum passt.

### <a name="return-value"></a>Rückgabewert

Die Höhe des Elements gedruckt.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode, um eine schlüsselzuordnung-Element im Dialogfeld Drucken. Standardmäßig gibt diese Methode Befehlsnamen, Tastenkombinationen und Befehls-Beschreibung des Elements.

##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns

Wird aufgerufen, durch das Framework Beschriftungen für die Spalten in der internen Steuerelement festlegen, die Karten-Steuerelement auf der Tastatur unterstützt.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Hinweise

Standardmäßig ruft diese Methode die Beschriftungen für die Spalten aus drei Ressourcen ab. Die Beschriftung der Befehl-Spalte wird von IDS_AFXBARRES_COMMAND, die Schlüsselspalte Beschriftung von IDS_AFXBARRES_KEYS ist und die Beschriftung der Description-Spalte wird von IDS_AFXBARRES_DESCRIPTION.

##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap

Vom Framework aufgerufen, wenn ein Benutzer klickt der **Drucken** Schaltfläche.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Hinweise

Die `PrintKeyMap` Methode gibt den zugeordnet. Er startet einen neuen Druckauftrag und ruft dann wiederholt die [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) und [CMFCKeyMapDialog::OnPrintItem](#onprintitem) Methoden, bis alle Schlüssel Zuordnungen gedruckt werden.

##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth

Wird aufgerufen, durch das Framework die Breite der Spalten in der internen Steuerelement festlegen, die Karten-Steuerelement auf der Tastatur unterstützt.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird die interne Liste des Steuerelements Spalten auf eine standardmäßige Breite. Zunächst wird die Breite der Verknüpfung Spalte berechnet. Klicken Sie dann ein Drittel der verbleibenden Breite der Spalte zugeordnet, und die restlichen zwei Drittel der Spalte "Beschreibung" zugeordnet.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)
