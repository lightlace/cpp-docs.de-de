---
title: CRichEditView-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
dev_langs:
- C++
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 353a45cad513e9c862b6ae6c15ab5383d3d65d48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378955"
---
# <a name="cricheditview-class"></a>CRichEditView-Klasse
Mit [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der MFC Dokument-Ansichtsarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|Erstellt ein `CRichEditView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Verschiebt Sie ein Dialogfeld, sodass er die aktuelle Auswahl überaus nicht.|  
|[CRichEditView::CanPaste](#canpaste)|Erfahren Sie, ob die Zwischenablage Daten enthält, die in die rich-Edit-Ansicht eingefügt werden können.|  
|[CRichEditView::DoPaste](#dopaste)|Fügt ein OLE-Element in die rich-Edit-Sicht.|  
|[CRichEditView::FindText](#findtext)|Sucht nach dem angegebenen Text, den Wartecursor aufrufen.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|Sucht nach dem angegebenen Text.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Ruft die Attribute für die aktuelle Auswahl formatieren von Zeichen ab.|  
|[CRichEditView::GetDocument](#getdocument)|Ruft einen Zeiger auf den zugehörigen [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Ruft das OLE-Element, das derzeit in-Place aktiv in der rich-Edit-Ansicht ab.|  
|[CRichEditView::GetMargins](#getmargins)|Ruft die Ränder für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetPageRect](#getpagerect)|Ruft das Rechteck Seite für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Ruft das Papierformat für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Ruft die Attribute für die aktuelle Auswahl formatieren von Absätzen ab.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Ruft das Drucken Rechteck für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Ruft die Breite des drucken für diese rich-Edit-Ansicht ab.|  
|[CRichEditView:: GetRichEditCtrl](#getricheditctrl)|Ruft das rich-Edit-Steuerelement ab.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|Ruft das ausgewählte Element aus der rich-Edit-Ansicht ab.|  
|[CRichEditView::GetTextLength](#gettextlength)|Ruft die Länge des Texts in der rich-Edit-Ansicht ab.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Ruft die Anzahl von Zeichen oder Bytes in der rich-Edit-Ansicht ab. Liste der erweiterten Flag für die Methode zum Bestimmen der Länge.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Fügt eine Datei als OLE-Element.|  
|[CRichEditView::InsertItem](#insertitem)|Fügt ein neues Element als OLE-Element.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Erfahren Sie, ob die Zwischenablage Daten in einem rich-Edit oder Text-Format enthält.|  
|[CRichEditView::OnCharEffect](#onchareffect)|Schaltet die für die aktuelle Auswahl formatieren von Zeichen an.|  
|[CRichEditView::OnParaAlign](#onparaalign)|Ändert die Ausrichtung der Absätze.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Aktualisiert die Benutzeroberfläche für Öffentliche Memberfunktionen Zeichen.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Aktualisiert die Benutzeroberfläche für Öffentliche Memberfunktionen Absatz an.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|Formatiert den angegebenen Text innerhalb des angegebenen Rechtecks.|  
|[CRichEditView::PrintPage](#printpage)|Formatiert den angegebenen Text innerhalb der angegebenen Seite.|  
|[CRichEditView::SetCharFormat](#setcharformat)|Legt die Attribute für die aktuelle Auswahl formatieren.|  
|[CRichEditView::SetMargins](#setmargins)|Legt die Ränder für diese Rich Bearbeiten Ansicht.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Legt das Papierformat für diese rich-Edit-Ansicht fest.|  
|[CRichEditView::SetParaFormat](#setparaformat)|Legt die Attribute für die aktuelle Auswahl formatieren von Absätzen fest.|  
|[CRichEditView::TextNotFound](#textnotfound)|Setzt den internen Suche Zustand des Steuerelements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|Ruft eine Zwischenablage-Datenobjekt für einen Bereich in dieser rich-Edit-Ansicht ab.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|Ruft ein Kontextmenü für die Verwendung auf einer rechten Maustaste unten ab.|  
|[CRichEditView::IsSelected](#isselected)|Gibt an, ob das angegebene OLE-Element oder nicht ausgewählt ist.|  
|[CRichEditView::OnFindNext](#onfindnext)|Sucht das nächste Vorkommen einer Teilzeichenfolge.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Aktualisiert eine Sicht, die beim ersten an ein Dokument angefügt.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Ruft die systemeigene Daten aus einem OLE-Element ab.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Legt die Druckeigenschaften für das angegebene Gerät fest.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|Ersetzt alle Vorkommen einer angegebenen Zeichenfolge durch eine neue Zeichenfolge an.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|Ersetzt die aktuelle Markierung.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Verarbeitet die Benachrichtigung für Benutzer, die der angeforderte Text nicht gefunden wurde.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Fragt ab, zu den Daten auf den `IDataObject`.|  
|[CRichEditView::WrapChanged](#wrapchanged)|Passt das Zielgerät für die Ausgabe für diese Rich--Sicht Edit, basierend auf den Wert des `m_nWordWrap`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Gibt den Umfang des Einzugs für Listen mit Aufzählungszeichen.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Gibt an, die Word-Wrap-Einschränkungen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer eingeben kann, und Bearbeiten von Text. Der Text kann Zeichen- und absatzformatierung zugewiesen werden und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die Formatierung von Text an. Komponenten der Benutzeroberfläche zum Formatierungsvorgänge für den Benutzer verfügbar machen muss jedoch eine Anwendung implementiert werden.  
  
 `CRichEditView` der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc` verwaltet die Liste der OLE-Clientelemente, die in der Ansicht sind. `CRichEditCntrItem` OLE-Clientelement erläutert Container-Seite.  
  
 Diese allgemeinen Windows-Steuerelements (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandte Klassen) ist verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 und höher.  
  
 Ein Beispiel für eine rich-Edit-Ansicht in einer MFC_Anwendung verwenden, finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) beispielanwendung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="adjustdialogposition"></a>  CRichEditView::AdjustDialogPosition  
 Mit dieser Funktion wird zum angegebenen Dialogfeld verschieben, sodass sie nicht die aktuelle Auswahl verdeckt.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>Parameter  
 *pDlg*  
 Zeiger auf eine `CDialog` Objekt.  
  
##  <a name="canpaste"></a>  CRichEditView::CanPaste  
 Rufen Sie diese Funktion, um zu bestimmen, ob die Zwischenablage Informationen enthält, die in die rich-Edit-Sicht eingefügt werden können.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zwischenablage Daten in einem Format enthält, diese rich-Edit-Ansicht annehmen kann; andernfalls 0.  
  
##  <a name="cricheditview"></a>  CRichEditView::CRichEditView  
 Mit dieser Funktion wird zum Erstellen einer `CRichEditView` Objekt.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>  CRichEditView::DoPaste  
 Mit dieser Funktion wird zum Einfügen von OLE-Element in `dataobj` in diese Rich-edit-Dokument-/Ansichtarchitektur.  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>Parameter  
 `dataobj`  
 Die [COleDataObject](../../mfc/reference/coledataobject-class.md) mit den Daten einfügen.  
  
 `cf`  
 Das gewünschte Format der Zwischenablage.  
  
 `hMetaPict`  
 Der Metadatei, die das einzufügende Element darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion als Teil der Standardimplementierung von [QueryAcceptData](#queryacceptdata).  
  
 Diese Funktion bestimmt den Typ der Elemente, die basierend auf den Ergebnissen des Handlers für Inhalte einfügen eingefügt. Wenn `cf` gleich 0 ist, das neue Element verwendet die aktuelle Elementsymbol Darstellung. Wenn `cf` ungleich NULL ist und `hMetaPict` nicht **NULL**, verwendet das neue Element `hMetaPict` für seine Darstellung.  
  
##  <a name="findtext"></a>  CRichEditView::FindText  
 Mit dieser Funktion wird zum angegebenen Text suchen und festlegen, dass die aktuelle Auswahl werden.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Enthält die zu suchende Zeichenfolge.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.  
  
 `bWord`  
 Gibt an, ob die Suche nur ganzes Wort nicht Teile von Wörtern übereinstimmen.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **"true"**, die suchrichtung wird am Ende des Puffers. Wenn **"false"**, die suchrichtung an den Anfang des Puffers ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `lpszFind` Text gefunden wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zeigt den Wartecursor während des Suchvorgangs angibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple  
 Mit dieser Funktion wird zum angegebenen Text suchen und festlegen, dass die aktuelle Auswahl werden.  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Enthält die zu suchende Zeichenfolge.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.  
  
 `bWord`  
 Gibt an, ob die Suche nur ganzes Wort nicht Teile von Wörtern übereinstimmen.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **"true"**, die suchrichtung wird am Ende des Puffers. Wenn **"false"**, die suchrichtung an den Anfang des Puffers ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `lpszFind` Text gefunden wird; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection  
 Mit dieser Funktion wird zum Abrufen der Attribute der aktuellen Auswahl formatieren von Zeichen.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Struktur, die die Attribute der aktuellen Auswahl formatieren von Zeichen enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) Nachricht und die [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData  
 Das Framework ruft diese Funktion als Teil der Verarbeitung der [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315).  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>Parameter  
 `lpchrg`  
 Zeiger auf die [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur des Bereichs von Zeichen (und OLE-Elemente), kopieren Sie auf das Datenobjekt, das gemäß Angabe `lplpdataobj`.  
  
 `dwReco`  
 Zwischenablage Vorgang Flag. Dabei kann es sich um einen der folgenden Werte sein.  
  
- **RECO_COPY** in die Zwischenablage kopieren.  
  
- **RECO_CUT** Ausschneiden in die Zwischenablage.  
  
- **RECO_DRAG** ziehen Vorgang (Drag & Drop).  
  
- **RECO_DROP** Drop-Vorgangs (Drag & Drop).  
  
- **RECO_PASTE** aus der Zwischenablage einfügen.  
  
 `lpRichDataObj`  
 Zeiger auf eine ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421) Objekt mit Daten aus der Zwischenablage aus der Rich-edit-Steuerelement ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 Zeiger auf die Zeigervariable, die die Adresse des empfängt die `IDataObject` Objekt, das im angegebenen Bereich darstellt. die `lpchrg` Parameter. Der Wert des `lplpdataobj` wird ignoriert, wenn ein Fehler zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert berichterstellung den Erfolg des Vorgangs. Weitere Informationen zu `HRESULT`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert gibt Erfolg an **IRichEditOleCallback::GetClipboardData** gibt die `IDataObject` zugreift `lplpdataobj`ist, andernfalls wird der zugreift Entitätencontainer zurückgegeben `lpRichDataObj`. Überschreiben Sie diese Funktion eine eigene Zwischenablagedaten bereitzustellen. Gibt die standardmäßige Implementierung dieser Funktion **E_NOTIMPL**.  
  
 Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) im Windows SDK und finden Sie unter ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421) im Windows SDK.  
  
##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu  
 Das Framework ruft diese Funktion als Teil der Verarbeitung der [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317).  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>Parameter  
 *seltyp*  
 Der Typ der Markierung. Die Typwerte Auswahl werden im Abschnitt "Hinweise" beschrieben.  
  
 `lpoleobj`  
 Zeiger auf eine **OLEOBJECT** Struktur, die der ersten ausgewählten OLE-Objekts angibt, wenn die Auswahl mindestens ein OLE-Elemente enthält. Wenn die Auswahl keine Elemente enthält `lpoleobj` ist **NULL**. Die **OLEOBJECT** Struktur enthält einen Zeiger auf ein OLE-Objekt-V-Tabelle.  
  
 `lpchrg`  
 Zeiger auf eine [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur, die die aktuelle Auswahl enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das Kontextmenü.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist eine übliche Teil der rechten Maustaste unten Verarbeitung.  
  
 Die Auswahltyp kann eine beliebige Kombination der folgenden Flags werden:  
  
- `SEL_EMPTY` Gibt an, dass keine aktuelle Auswahl vorhanden ist.  
  
- `SEL_TEXT` Gibt an, dass die aktuelle Auswahl Text enthält.  
  
- `SEL_OBJECT` Gibt an, dass die aktuelle Auswahl mindestens ein OLE-Element enthält.  
  
- `SEL_MULTICHAR` Gibt an, dass die aktuelle Auswahl mehr als ein Zeichen des Texts enthält.  
  
- `SEL_MULTIOBJECT` Gibt an, dass die aktuelle Auswahl mehrere OLE-Objekts enthält.  
  
 Gibt die standardmäßige Implementierung **NULL**. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) im Windows SDK.  
  
 Weitere Informationen zu den **OLEOBJECT** geben, finden Sie im Artikel OLE-Datenstrukturen und Struktur-Zuordnung in der *OLE-Wissensdatenbank*.  
  
##  <a name="getdocument"></a>  CRichEditView::GetDocument  
 Mit dieser Funktion können Sie einen Zeiger auf die `CRichEditDoc` dieser Ansicht zugeordnet.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) mit Ihrem `CRichEditView` Objekt.  
  
##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem  
 Aufruf dieser Funktion zum Abrufen des OLE Element, das derzeit aktiviert ist, direkt in diese `CRichEditView` Objekt.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen, direkte aktive [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt in dieser Ansicht rich-Edit; **NULL** Falls kein OLE-Element gibt es derzeit im aktiven Zustand direktes ist.  
  
##  <a name="getmargins"></a>  CRichEditView::GetMargins  
 Mit dieser Funktion wird zum Abrufen der aktuellen Ränder, die beim Drucken verwendet.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ränder verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
##  <a name="getpagerect"></a>  CRichEditView::GetPageRect  
 Mit dieser Funktion wird zum Abrufen der Dimensionen von der Seite, die beim Drucken verwendet.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Grenzen der Seite verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert basiert auf das Papierformat.  
  
##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize  
 Mit dieser Funktion wird zum Abrufen der aktuellen Papierformat.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Papierformat verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection  
 Mit dieser Funktion wird zum Abrufen der Attribute der aktuellen Auswahl formatieren von Absätzen.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Struktur, die die Attribute der aktuellen Auswahl formatieren von Absätzen enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) Nachricht und [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Struktur im Windows SDK.  
  
##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect  
 Rufen Sie diese Funktion, um die Grenzen des Druckbereichs innerhalb des Rechtecks Seite abrufen.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Grenzen des dem Bildbereich verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth  
 Mit dieser Funktion wird um die Breite des Druckbereichs zu bestimmen.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des Druckbereichs, gemessen in `MM_TWIPS`.  
  
##  <a name="getricheditctrl"></a>  CRichEditView:: GetRichEditCtrl  
 Mit dieser Funktion wird zum Abrufen der [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) zugeordnete Objekt der `CRichEditView` Objekt.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CRichEditCtrl` Objekt für diese Ansicht.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem  
 Mit dieser Funktion wird zum Abrufen von OLE-Element (eine `CRichEditCntrItem` Objekt) in diesem ausgewählten `CRichEditView` Objekt.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) ausgewählte Objekt in der `CRichEditView` Objekt. **NULL** Wenn kein Element in dieser Ansicht ausgewählt ist.  
  
##  <a name="gettextlength"></a>  CRichEditView::GetTextLength  
 Mit dieser Funktion wird zum Abrufen der Länge des Texts in diesem `CRichEditView` Objekt.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Texts in diesem `CRichEditView` Objekt.  
  
##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx  
 Rufen Sie diese Memberfunktion zum Berechnen der Länge des Texts in diesem `CRichEditView` Objekt.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Der Wert gibt die Methode zum Bestimmen der Länge verwendet werden. Dieser Member kann eine oder mehrere der Werte im Flags-Mitglied der aufgeführten [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) im Windows SDK beschrieben.  
  
 `uCodePage`  
 Die Codepage für die Übersetzung (für ANSI-Codepage, 1200 für Unicode CP_ACP verwendet).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen oder Bytes in den Edit-Steuerelement. Wenn nicht kompatible Flags, im festgelegt wurden `dwFlags`, diese Memberfunktion gibt `E_INVALIDARG`.  
  
### <a name="remarks"></a>Hinweise  
 `GetTextLengthEx` Stellt zusätzliche Methoden zum Bestimmen der Länge des Texts an. Die Funktionalität des Rich Edit 2.0 unterstützt. Weitere Informationen finden Sie unter [über Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) im Windows SDK.  
  
##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject  
 Mit dieser Funktion können Sie die angegebene Datei einfügen (als eine [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt) in einem RichEdit-Ansicht bearbeiten.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Zeichenfolge, die mit dem Namen der Datei, die eingefügt werden soll.  
  
##  <a name="insertitem"></a>  CRichEditView::InsertItem  
 Mit dieser Funktion wird zum Einfügen einer [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt in eine rich-Edit-Sicht.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Element, das eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert, der angibt, der des Erfolgs des Einfügevorgangs.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu `HRESULT`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) im Windows SDK.  
  
##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat  
 Mit dieser Funktion wird zum bestimmen, ob `cf` ist ein Zwischenablageformat also Text, rich-Text oder rich-Text mit OLE-Elementen.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 Das Format der Zwischenablage von Interesse sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `cf` ist eine umfangreiche bearbeiten oder Text das Format der Zwischenablage.  
  
##  <a name="isselected"></a>  CRichEditView::IsSelected  
 Rufen Sie diese Funktion, um zu bestimmen, ob das angegebene OLE-Element in dieser Ansicht derzeit ausgewählt ist.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDocItem`  
 Zeiger auf ein Objekt in der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Ihre Klasse abgeleitete Sicht eine andere Methode zur Behandlung von der Auswahl von OLE-Elementen verfügt.  
  
##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent  
 Den Einzug für Punkt-Elemente in einer Liste; in der Standardeinstellung, 720 Einheiten 1/2 Zoll.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap  
 Gibt den Typ der Zeilenumbruch für diese rich-Edit-Ansicht an.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Hinweise  
 Einer der folgenden Werte:  
  
- `WrapNone` Gibt keine automatische Wortumbruch an.  
  
- `WrapToWindow` Gibt anhand der Breite des Fensters Wortumbruch an.  
  
- `WrapToTargetDevice` Gibt an, basierend auf den Merkmalen des Zielgeräts Wortumbruch.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::WrapChanged](#wrapchanged).  
  
##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect  
 Rufen Sie diese Funktion, um die zeichenformatierung Effekte für die aktuelle Auswahl umzuschalten.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMask`  
 Die Effekte so ändern Sie in der aktuellen Auswahl formatieren von Zeichen.  
  
 `dwEffect`  
 Die gewünschte Liste der zeichenformatierung Effekte aktivieren bzw. deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Aufruf dieser Funktion wird die Effekte der angegebenen Formatierung für die aktuelle Auswahl umgeschaltet.  
  
 Weitere Informationen zu den `dwMask` und `dwEffect` Parameter und deren mögliche Werte finden Sie unter den entsprechenden Datenmember des [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>  CRichEditView::OnFindNext  
 Wird vom Framework aufgerufen, bei der Verarbeitung von Befehlen aus dem Dialogfeld Suchen/Ersetzen.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Die zu suchende Zeichenfolge.  
  
 `bNext`  
 Die Richtung, gesucht werden soll: **"true"** angibt. **"False"**, bis.  
  
 `bCase`  
 Gibt an, ob die Suche Groß-/Kleinschreibung beachtet werden soll.  
  
 `bWord`  
 Gibt an, ob die Suche auf ganze Wörter nur oder nicht übereinstimmen.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Suchen von Text in der `CRichEditView`. Überschreiben Sie diese Funktion, um Suchkriterien für die Klasse abgeleitete Sicht zu ändern.  
  
##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber bevor die Ansicht anfänglich angezeigt wird.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) Memberfunktion ohne Hinweis Informationen (d. h. unter Verwendung der Standardwerte von 0 für die `lHint` Parameter und **NULL** für die `pHint` Parameter). Überschreiben Sie diese Funktion, um die einmalige Initialisierung auszuführen, die Informationen über das Dokument erfordert. Beispielsweise verfügt die Anwendung Dokumente fester Größe, können dieser Funktion Sie zum Durchführen eines Bildlaufs Grenzwerte für eine Sicht basierend auf die Größe des Dokuments zu initialisieren. Wenn Ihre Anwendung variabler Größe von Dokumenten unterstützt, verwenden `OnUpdate` zum Aktualisieren der Bildlauf schränkt jedes Mal das Dokument geändert wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::m_nWordWrap](#m_nwordwrap).  
  
##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject  
 Verwenden Sie diese Funktion wird zum Laden von systemeigener Daten von einem eingebetteten Element.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>Parameter  
 *lpStg*  
 Zeiger auf eine [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0;  
  
### <a name="remarks"></a>Hinweise  
 In der Regel würde diesem Zweck erstellen eine [COleStreamFile](../../mfc/reference/colestreamfile-class.md) um die `IStorage`. Die `COleStreamFile` angefügt werden können, um ein Archiv und [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) aufgerufen, um die Daten zu laden.  
  
 Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) im Windows SDK.  
  
##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign  
 Mit dieser Funktion wird zum Ändern der absatzausrichtung für die ausgewählten Absätze.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>Parameter  
 `wAlign`  
 Die gewünschte absatzausrichtung. Einer der folgenden Werte:  
  
- `PFA_LEFT` Richten Sie die Absätze mit dem linken Rand an.  
  
- `PFA_RIGHT` Richten Sie die Absätze mit den rechten Rand an.  
  
- `PFA_CENTER` Zentrieren Sie die Absätze zwischen dem Rand an.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged  
 Überschreiben Sie diese Funktion, um Eigenschaften für diese rich-Edit-Ansicht zu ändern, wenn der Drucker ändert.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>Parameter  
 `dcPrinter`  
 Ein [CDC](../../mfc/reference/cdc-class.md) Objekt für den neuen Drucker.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung legt das Papierformat auf die physische Höhe und Breite für das Ausgabegerät (Drucker) fest. Es ist keine Gerätekontext zugeordnet `dcPrinter`, bei der Standardimplementierung wird das Papierformat auf 8,5 x 11 Zoll.  
  
##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll  
 Wird vom Framework aufgerufen, bei der Verarbeitung von ersetzen alle Befehle aus dem Dialogfeld ersetzen.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text ersetzt werden.  
  
 `lpszReplace`  
 Der Ersetzungstext.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.  
  
 `bWord`  
 Gibt an, ob die Suche ganze Wörtern suchen auswählen muss.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion ersetzt alle Vorkommen des angegebenen Text mit einer anderen Zeichenfolge. Überschreiben Sie diese Funktion, um Suchkriterien für diese Ansicht zu ändern.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel  
 Vom Framework aufgerufen, bei der Verarbeitung von Replace-Befehle aus dem Dialogfeld ersetzen.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text ersetzt werden.  
  
 `bNext`  
 Gibt die Richtung der Suche: **"true"** ist nicht verfügbar; **"False"**, bis.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.  
  
 `bWord`  
 Gibt an, ob die Suche ganze Wörtern suchen auswählen muss.  
  
 `lpszReplace`  
 Der Ersetzungstext.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie ein Vorkommen des angegebenen Text durch eine andere Zeichenfolge ersetzen. Überschreiben Sie diese Funktion, um Suchkriterien für diese Ansicht zu ändern.  
  
##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound  
 Vom Framework aufgerufen, wenn eine Suche ein Fehler auftritt.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text wurde nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Ausgabe von änderungsbenachrichtigungen eine [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356).  
  
 Weitere Informationen finden Sie unter [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect  
 Das Framework ruft diese Funktion, um den UI-Befehl für Zeichen Auswirkungen Befehle zu aktualisieren.  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt.  
  
 `dwMask`  
 Gibt die Maske Formatieren von Zeichen an.  
  
 `dwEffect`  
 Gibt den Effekt Formatieren von Zeichen an.  
  
### <a name="remarks"></a>Hinweise  
 Die Maske `dwMask` gibt an, welches Formatierungsattribute zu überprüfende Zeichen. Die Flags `dwEffect` Liste der Attribute für den Satz/löschen Formatieren von Zeichen.  
  
 Weitere Informationen zu den `dwMask` und `dwEffect` Parameter und deren mögliche Werte finden Sie unter den entsprechenden Datenmember des [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign  
 Das Framework ruft diese Funktion, um den UI-Befehl für den Absatz Auswirkungen Befehle zu aktualisieren.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt.  
  
 `wAlign`  
 Die absatzausrichtung zu überprüfen. Einer der folgenden Werte:  
  
- `PFA_LEFT` Richten Sie die Absätze mit dem linken Rand an.  
  
- `PFA_RIGHT` Richten Sie die Absätze mit den rechten Rand an.  
  
- `PFA_CENTER` Zentrieren Sie die Absätze zwischen dem Rand an.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect  
 Mit dieser Funktion können Sie einen Bereich von Text in einem rich-Edit-Steuerelement passt formatieren *RectLayout* für das Gerät gemäß `pDC`.  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Zeiger zu einem Gerätekontext zum Bereich "Ausgabe".  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Ausgabebereich definiert.  
  
 `nIndexStart`  
 Nullbasierte Index des ersten Zeichens formatiert werden.  
  
 `nIndexStop`  
 Nullbasierte Index des letzten Zeichens formatiert werden.  
  
 *bOutput*  
 Gibt an, ob der Text gerendert werden soll. Wenn **"false"**, der Text einfach gemessen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Zeichens, die in den Ausgabebereich plus 1 entspricht.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel wird dieser Aufruf folgen, durch einen Aufruf von [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) durch die die Ausgabe generiert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="printpage"></a>  CRichEditView::PrintPage  
 Mit dieser Funktion können Sie einen Bereich von Text in einem rich-Edit-Steuerelement für das Ausgabegerät gemäß formatieren `pDC`.  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Zeiger zu einem Gerätekontext für Seitenausgabe.  
  
 `nIndexStart`  
 Nullbasierte Index des ersten Zeichens formatiert werden.  
  
 `nIndexStop`  
 Nullbasierte Index des letzten Zeichens formatiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Zeichens, die auf der Seite plus 1 entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Das Layout der einzelnen Seiten wird gesteuert, indem [GetPageRect](#getpagerect) und [GetPrintRect](#getprintrect). In der Regel wird dieser Aufruf folgen, durch einen Aufruf von [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) durch die die Ausgabe generiert.  
  
 Beachten Sie, dass Ränder relativ zur physischen Seite, nicht die logische Seite. Daher werden Ränder 0 (null) häufig clip-den Text, da viele Drucker nicht druckbare Bereiche auf der Seite haben. Um zu vermeiden, kürzen den Text, rufen Sie [SetMargins](#setmargins) und angemessene Ränder vor dem Druck festlegen.  
  
##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData  
 Wird aufgerufen, durch das Framework um ein Objekt in die rich-Edit einzufügen.  
  
```  
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,  
    CLIPFORMAT* lpcfFormat,  
    DWORD dwReco,  
    BOOL bReally,  
    HGLOBAL hMetaFile);
```  
  
### <a name="parameters"></a>Parameter  
 *lpdataobj*  
 Zeiger auf die ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421) Abfrage.  
  
 *lpcfFormat*  
 Ein Zeiger auf das akzeptable Datenformat.  
  
 `dwReco`  
 Nicht verwendet.  
  
 *bReally*  
 Gibt an, ob der Einfügevorgang oder nicht fortgesetzt werden soll.  
  
 `hMetaFile`  
 Ein Handle für die Metadatei, die zum Zeichnen des Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert berichterstellung den Erfolg des Vorgangs.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um andere Organisation der COM-Elemente in der abgeleiteten Dokumentklasse zu behandeln. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen zu `HRESULT` und `IDataObject`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) und ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421)bzw., im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat  
 Mit dieser Funktion können Sie die Formatierungsattribute für den neuen Text in diesem Zeichensatz `CRichEditView` Objekt.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Struktur, die die neue Standardeinstellung zeichenformatierung Attribute enthält.  
  
### <a name="remarks"></a>Hinweise  
 Nur die Attribute, die gemäß der **DwMask** Mitglied `cf` , die von dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) Nachricht und [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>  CRichEditView::SetMargins  
 Mit dieser Funktion wird zum Festlegen von Druckränder für diese rich-Edit-Ansicht.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>Parameter  
 *rectMargin*  
 Die neue Randwerte für das Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [m_nWordWrap an](#m_nwordwrap) ist `WrapToTargetDevice`, rufen Sie [WrapChanged](#wrapchanged) nach der Verwendung dieser Funktion Druckeigenschaften anpassen.  
  
 Beachten Sie, die die Ränder von verwendet [PrintPage](#printpage) sind relativ zu der physischen Seite, nicht die logische Seite. Daher werden Ränder 0 (null) häufig clip-den Text, da viele Drucker nicht druckbare Bereiche auf der Seite haben. Um zu vermeiden, kürzen den Text, rufen Sie die Verwendung `SetMargins` angemessenen Drucker Ränder vor dem Druck festlegen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize  
 Mit dieser Funktion wird zum Festlegen des Papierformats für diese rich-Edit-Ansicht zu drucken.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>Parameter  
 *sizePaper*  
 Die neuen Werte der Dokument-Größe für das Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [m_nWordWrap an](#m_nwordwrap) ist `WrapToTargetDevice`, rufen Sie [WrapChanged](#wrapchanged) nach der Verwendung dieser Funktion Druckeigenschaften anpassen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat  
 Mit dieser Funktion wird zum Festlegen der Attribute für die aktuelle Auswahl in diesem Formatieren von Absätzen `CRichEditView` Objekt.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Parameter  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Struktur, die den neuen Standard enthält Absatz Formatierungsattribute.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die Attribute, die gemäß der **DwMask** Mitglied `pf` , die von dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) Nachricht und [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>  CRichEditView::TextNotFound  
 Mit dieser Funktion können Sie den internen Suche Status zurücksetzen der [CRichEditView](../../mfc/reference/cricheditview-class.md) Steuerelement nach einem fehlgeschlagenen Aufruf von [FindText](#findtext).  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Enthält die Zeichenfolge, die nicht gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, diese Methode aufgerufen werden, sofort nach der fehlgeschlagene Aufrufe von [FindText](#findtext) , damit die Suche internen Zustand des Steuerelements ordnungsgemäß zurückgesetzt wird.  
  
 Die `lpszFind` -Parameter muss den gleichen Inhalt wie die bereitgestellte Zeichenfolge enthalten [FindText](#findtext). Nach dem Zurücksetzen des Zustands des internen Suche, diese Methode ruft die [OnTextNotFound](#ontextnotfound) Methode mit der angegebenen Suchzeichenfolge.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged  
 Mit dieser Funktion werden, wenn sich die Druckeigenschaften geändert haben ( [SetMargins](#setmargins) oder [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, die so zu ändern, das Rich--Ansicht Edit auf Änderungen in antwortet [m_nWordWrap an](#m_nwordwrap) oder die Druckeigenschaften ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)
