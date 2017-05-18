---
title: Klasse CMFCKeyMapDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCKeyMapDialog class
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6599f5c3cda6eb407f4545d42528c1c68950b94c
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog-Klasse
Die `CMFCKeyMapDialog` Klasse unterstützt ein Steuerelement, das Befehlen Tastaturtasten zuordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Erstellt ein `CMFCKeyMapDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](#domodal)|Zeigt ein Dialogfeld Tastatur Zuordnung.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Aufgerufen, um eine Zeichenfolge zu erstellen, die eine wichtige Zuordnung beschreibt. Standardmäßig enthält die Zeichenfolge den Namen des Befehls verwendeten Tastenkombinationen und die Beschreibung der Verknüpfung-Schlüssels.|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Ruft eine Zeichenfolge, die eine Liste der Tastenkombinationen, die dem angegebenen Befehl zugeordnete enthält.|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Vom Framework aufgerufen, bevor ein neues Element in der internen Listensteuerelement eingefügt wird, die die Tastatur-Mapping-Steuerelement unterstützt.|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Aufgerufen, um den Kopf für das Tastaturlayout auf einer neuen Seite auszudrucken.|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Aufgerufen, um eine Tastatur Mapping-Element zu drucken.|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Vom Framework aufgerufen Beschriftungen für die Spalten in der internen Listensteuerelement festlegen, die die Tastatur-Mapping-Steuerelement unterstützt.|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Vom Framework aufgerufen, wenn ein Benutzer klickt der **Drucken** Schaltfläche.|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Aufgerufen, um die Breite der Spalten in der internen Listensteuerelement festzulegen, die Tastatur-Mapping-Steuerelement unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CMFCKeyMapDialog` Klasse, um ein Dialogfeld mit veränderbarer Größe Tastatur Zuordnung zu implementieren. Das Dialogfeld verwendet ein Listenansicht-Steuerelement, um Tastenkombinationen und die entsprechenden Befehle anzuzeigen.  
  
 Verwenden der `CMFCKeyMapDialog` -Klasse in einer Anwendung, übergeben Sie einen Zeiger auf das Hauptrahmenfenster als Parameter an die `CMFCKeyMapDialog` Konstruktor. Rufen Sie dann die `DoModal` Methode, um ein modales Dialogfeld starten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxkeymapdialog.h  
  
##  <a name="cmfckeymapdialog"></a>CMFCKeyMapDialog::CMFCKeyMapDialog  
 Erstellt ein `CMFCKeyMapDialog`-Objekt.  
  
```  
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bEnablePrint=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParentFrame`  
 Ein Zeiger auf das übergeordnete Fenster von der `CMFCKeyMapDialog` Objekt.  
  
 [in] `bEnablePrint`  
 `TRUE`Wenn die Liste der Tastenkombinationen gedruckt werden kann; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCKeyMapDialog` Klasse. Dieses Beispiel ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&21;](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CMFCKeyMapDialog::DoModal  
 Zeigt ein Dialogfeld Tastatur Zuordnung.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Ganzzahl mit Vorzeichen, z. B. `IDOK` oder `IDCANCEL`, d. h. zum Übergeben der [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) Methode. Die Methode wird wiederum das Dialogfeld geschlossen. Weitere Informationen finden Sie unter [Methode CDialog:: DoModal](../../mfc/reference/cdialog-class.md#domodal).  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Tastatur Zuordnung können Sie auswählen und verschiedene Kategorien von Befehlen Tastenkombinationen zuweisen. Darüber hinaus können Sie die ausgewählten Zugriffstasten und deren Beschreibung in die Zwischenablage kopieren.  
  
##  <a name="formatitem"></a>CMFCKeyMapDialog::FormatItem  
 Aufgerufen, um eine Zeichenfolge zu erstellen, die eine wichtige Zuordnung beschreibt. Standardmäßig enthält die Zeichenfolge den Namen des Befehls verwendeten Tastenkombinationen und die Beschreibung der Verknüpfung-Schlüssels.  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItem`  
 Der nullbasierte Index eines Elements in der internen Liste der wichtigsten Zuordnungen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das den formatierten Text enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcommandkeys"></a>CMFCKeyMapDialog::GetCommandKeys  
 Ruft einen Zeichenfolgenwert ab. Die Zeichenfolge enthält eine Liste der Tastenkombinationen, die mit einem bestimmten Befehl zugeordnet sind.  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Eine Befehls-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine durch Semikolons getrennte (';') Liste mit Tastenkombinationen, die den angegebenen Befehl zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oninsertitem"></a>CMFCKeyMapDialog::OnInsertItem  
 Vom Framework aufgerufen, bevor ein neues Element in ein Steuerelement für die interne Liste eingefügt wird, die die Tastatur-Mapping-Steuerelement unterstützt.  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Symbolleisten-Schaltfläche, mit dem Befehlsname und Beschreibung Tastatur Tastenkombination zuordnen. Die Zuordnung-Element wird in einem Steuerelement für die interne Liste gespeichert.  
  
 [in] `nItem`  
 Ein nullbasierter Index, der angibt, wo Sie das neue Element der Zuordnung in der internen Liste-Steuerelement einfügen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onprintheader"></a>CMFCKeyMapDialog::OnPrintHeader  
 Aufgerufen, um den Kopf für das Tastaturlayout auf einer neuen Seite auszudrucken.  
  
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
 Die Seitenzahl der Seite gedruckt werden soll.  
  
 [in] `cx`  
 Der horizontale Offset des Headers, in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die Höhe der gedruckten Text. Weitere Informationen finden Sie im Abschnitt "Return Value" des [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode das Tastaturlayout zu drucken. Standardmäßig gibt diese Methode die Seitenzahl, der Anwendungsname und der Titel des Dateidialogfelds.  
  
##  <a name="onprintitem"></a>CMFCKeyMapDialog::OnPrintItem  
 Aufgerufen, um eine Tastatur Mapping-Element zu drucken.  
  
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
 Der nullbasierte Index des Elements, das Drucken.  
  
 [in] `y`  
 Der vertikale Offset zwischen dem oberen Rand der Seite und die Position des Elements.  
  
 [in] `cx`  
 Der horizontale Offset zwischen dem linken Rand der Seite und der Position des Elements.  
  
 [in] `bCalcHeight`  
 `TRUE`um die optimale Höhe für das Element drucken zu berechnen; `FALSE` das Element Drucken abgeschnitten, damit er den Standardzwischenraum passt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des gedruckten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um eine Zuordnung-Element im Dialogfeld Drucken. Standardmäßig gibt diese Methode des Elements Befehlsnamen, Tastenkombinationen und Befehl Beschreibung.  
  
##  <a name="onsetcolumns"></a>CMFCKeyMapDialog::OnSetColumns  
 Vom Framework aufgerufen Beschriftungen für die Spalten in der internen Listensteuerelement festlegen, die die Tastatur-Mapping-Steuerelement unterstützt.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ruft diese Methode die Beschriftungen für die Spalten aus drei Ressourcen. Die Befehl Spalte Beschriftung von IDS_AFXBARRES_COMMAND ist, die Schlüsselspalte Beschriftung von IDS_AFXBARRES_KEYS ist und die Beschriftung der Description-Spalte wird aus IDS_AFXBARRES_DESCRIPTION.  
  
##  <a name="printkeymap"></a>CMFCKeyMapDialog::PrintKeyMap  
 Vom Framework aufgerufen, wenn ein Benutzer klickt der **Drucken** Schaltfläche.  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `PrintKeyMap` Methode gibt die Zuordnung. Es wird einen neuen Druckauftrag initiiert und ruft dann wiederholt die [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) und [CMFCKeyMapDialog::OnPrintItem](#onprintitem) Methoden, bis alle Schlüssel Zuordnungen gedruckt werden.  
  
##  <a name="setcolumnswidth"></a>CMFCKeyMapDialog::SetColumnsWidth  
 Aufgerufen, um die Breite der Spalten in der internen Listensteuerelement festzulegen, die Tastatur-Mapping-Steuerelement unterstützt.  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die interne Liste Spalten des Steuerelements auf eine Standard-Breite. Zunächst wird die Breite der Spalte Schlüssel Kontextmenü berechnet. Klicken Sie dann ein Drittel der verbleibenden Breite in der Spalte zugeordnet ist, und die restlichen zwei Drittel der Description-Spalte zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)

