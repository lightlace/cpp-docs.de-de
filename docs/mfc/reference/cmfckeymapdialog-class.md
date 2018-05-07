---
title: CMFCKeyMapDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25d86a4797479fe3ee95dde162e22cde63aaa71e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Wird aufgerufen, durch das Framework eine Zeichenfolge zu erstellen, die eine wichtige Zuordnung beschreibt. Standardmäßig enthält die Zeichenfolge den Namen des Befehls, verwendeten Tastenkombinationen und die Beschreibung der Verknüpfung-Schlüssels.|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Ruft eine Zeichenfolge, die eine Liste der Tastenkombinationen, die den angegebenen Befehl zugeordnet enthält.|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Vom Framework aufgerufen, bevor ein neues Element in das interne Strukturelement-Steuerelement eingefügt wird, die das Steuerelement der Tastatur Zuordnung unterstützt.|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Wird aufgerufen, durch das Framework den Header für das Tastaturlayout auf einer neuen Seite gedruckt.|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Wird aufgerufen, durch das Framework So drucken Sie eine Tastatur Mapping-Element.|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Wird aufgerufen, durch das Framework Beschriftungen für die Spalten in das interne Strukturelement-Steuerelement festlegen, die das Steuerelement der Tastatur Zuordnung unterstützt.|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Vom Framework aufgerufen, wenn ein Benutzer klickt auf die **Drucken** Schaltfläche.|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Wird aufgerufen, durch das Framework die Breite der Spalten in das interne Strukturelement-Steuerelement festlegen, die das Steuerelement der Tastatur Zuordnung unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CMFCKeyMapDialog` Klasse, um ein Dialogfeld in der Größe veränderbaren Tastatur Zuordnung zu implementieren. Das Dialogfeld verwendet ein Listenansicht-Steuerelement zum Anzeigen von Tastenkombinationen und ihre zugeordneten Befehle.  
  
 Verwenden der `CMFCKeyMapDialog` -Klasse in einer Anwendung, übergeben Sie einen Zeiger an das Hauptrahmenfenster als Parameter an die `CMFCKeyMapDialog` Konstruktor. Rufen Sie anschließend die `DoModal` Methode, um ein modales Dialogfeld starten.  
  
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
 [in] `pWndParentFrame`  
 Ein Zeiger auf das übergeordnete Fenster eines der `CMFCKeyMapDialog` Objekt.  
  
 [in] `bEnablePrint`  
 `TRUE` Wenn die Liste mit Zugriffstasten gedruckt werden kann; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCKeyMapDialog` Klasse. In diesem Beispiel ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal  
 Zeigt im Dialogfeld für die Zuordnung einer Tastatur an.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Ganzzahl mit Vorzeichen, z. B. `IDOK` oder `IDCANCEL`, d. h. zum Übergeben der [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) Methode. Die Methode wird wiederum das Dialogfeld geschlossen. Weitere Informationen finden Sie unter [Methode CDialog:: DoModal](../../mfc/reference/cdialog-class.md#domodal).  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Zuordnung ermöglicht es Ihnen zu wählen und verschiedene Kategorien von Befehlen Zugriffstasten zuzuweisen. Darüber hinaus können Sie die ausgewählten Zugriffstasten sowie die Beschreibung in die Zwischenablage kopieren.  
  
##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem  
 Wird aufgerufen, durch das Framework eine Zeichenfolge zu erstellen, die eine wichtige Zuordnung beschreibt. Standardmäßig enthält die Zeichenfolge den Namen des Befehls, verwendeten Tastenkombinationen und die Beschreibung der Verknüpfung-Schlüssels.  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItem`  
 Der nullbasierte Index eines Elements in der internen Liste von Schlüssel-Zuordnungen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den formatierten Text enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys  
 Ruft einen Zeichenfolgenwert ab. Die Zeichenfolge enthält eine Liste der Tastenkombinationen, die einen bestimmten Befehl zugeordnet sind.  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Eine Befehls-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine durch Semikolons getrennt (';') Liste mit Tastenkombinationen, die den angegebenen Befehl zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem  
 Vom Framework aufgerufen, bevor ein neues Element in einer internen Strukturelement-Steuerelement eingefügt wird, die das Steuerelement der Tastatur Zuordnung unterstützt.  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Symbolleisten-Schaltfläche, die verwendet wird, um einen Befehlsnamen und eine Beschreibung eine Tastatur Tastenkombination zuordnen. Das schlüsselzuordnung-Element wird in einem Steuerelement für die interne Liste gespeichert.  
  
 [in] `nItem`  
 Ein nullbasierter Index, der angibt, wo der neue Schlüssel Zuordnungselement in das interne Strukturelement-Steuerelement eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader  
 Wird aufgerufen, durch das Framework den Header für das Tastaturlayout auf einer neuen Seite gedruckt.  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dc`  
 Der Gerätekontext für den Drucker.  
  
 [in] `nPage`  
 Die Seitenzahl der Seite zu drucken.  
  
 [in] `cx`  
 Der horizontale Offset des Headers, in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall die Höhe des gedruckten Texts. Weitere Informationen finden Sie im Abschnitt Rückgabewert [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode, um das Tastaturlayout drucken. Standardmäßig gibt diese Methode die Seitenzahl, Anwendungsname und Titel des Dateidialogfelds.  
  
##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem  
 Wird aufgerufen, durch das Framework So drucken Sie eine Tastatur Mapping-Element.  
  
```  
virtual int OnPrintItem(
    CDC& dc,  
    int nItem,  
    int y,  
    int cx,  
    BOOL bCalcHeight) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dc`  
 Der Gerätekontext des Druckers.  
  
 [in] `nItem`  
 Der nullbasierte Index des Elements, das gedruckt werden soll.  
  
 [in] `y`  
 Der vertikale Offset zwischen dem oberen Rand der Seite und die Position des Elements.  
  
 [in] `cx`  
 Der horizontale Offset zwischen dem linken Rand der Seite und die Position des Elements.  
  
 [in] `bCalcHeight`  
 `TRUE` um die optimale Höhe für das Drucken Element zu berechnen; `FALSE` drucken Element abgeschnitten, damit er den Standardzwischenraum passt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Elements gedruckt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um eine schlüsselzuordnung-Element im Dialogfeld Drucken. Standardmäßig gibt diese Methode des Elements Befehlsnamen, Tastenkombinationen und Beschreibung der Befehl.  
  
##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns  
 Wird aufgerufen, durch das Framework Beschriftungen für die Spalten in das interne Strukturelement-Steuerelement festlegen, die das Steuerelement der Tastatur Zuordnung unterstützt.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ruft diese Methode die Beschriftungen für die Spalten aus drei Ressourcen ab. Die Befehl Spalte Beschriftung aus IDS_AFXBARRES_COMMAND ist, ist die Schlüsselspalte Beschriftung IDS_AFXBARRES_KEYS und die Beschriftung der Description-Spalte aus IDS_AFXBARRES_DESCRIPTION ist.  
  
##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap  
 Vom Framework aufgerufen, wenn ein Benutzer klickt auf die **Drucken** Schaltfläche.  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `PrintKeyMap` Methode druckt die schlüsselzuordnung. Es wird einen neuen Druckauftrag initiiert und ruft dann wiederholt die [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) und [CMFCKeyMapDialog::OnPrintItem](#onprintitem) Methoden erst die Key Zuordnungen gedruckt werden.  
  
##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth  
 Wird aufgerufen, durch das Framework die Breite der Spalten in das interne Strukturelement-Steuerelement festlegen, die das Steuerelement der Tastatur Zuordnung unterstützt.  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die interne Liste an Standardeinstellung breiten Spalten des Steuerelements fest. Zunächst wird die Breite der Spalte Schlüssel Verknüpfung berechnet. Klicken Sie dann ein Drittel der verbleibenden Breite der Spalte zugeordnet ist, und die restlichen zwei Drittel der Description-Spalte zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)
