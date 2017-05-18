---
title: CRichEditView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- document/view architecture, rich edit controls
- OLE containers, rich edit
- rich edit controls, OLE container
- CRichEditView class
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
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
ms.openlocfilehash: 9f54ec0c8aae58828607b01973a263e458c30ddb
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditview-class"></a>CRichEditView-Klasse
Mit [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der Dokument-/Ansichtarchitektur von MFC bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|Erstellt ein `CRichEditView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Verschiebt Sie ein Dialogfeld, sodass er nicht die aktuelle Auswahl verdeckt wird.|  
|[CRichEditView::CanPaste](#canpaste)|Erfahren Sie, ob die Zwischenablage Daten enthält, die in die rich-Edit-Ansicht eingefügt werden kann.|  
|[CRichEditView::DoPaste](#dopaste)|Ein OLE-Element in dieser rich-Edit-Ansicht eingefügt.|  
|[CRichEditView::FindText](#findtext)|Sucht nach dem angegebenen Text, den Wartecursor aufrufen.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|Sucht den angegebenen Text.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Ruft die Attribute für die aktuelle Auswahl formatieren von Zeichen ab.|  
|[CRichEditView::GetDocument](#getdocument)|Ruft einen Zeiger auf den zugehörigen [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Ruft das OLE-Element, die derzeit in-Place aktiv in der rich-Edit-Ansicht ab.|  
|[CRichEditView::GetMargins](#getmargins)|Ruft die Ränder für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetPageRect](#getpagerect)|Ruft das Rechteck Seite dieser rich-Edit-Ansicht an.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Ruft die Papiergröße für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Ruft die Attribute für die aktuelle Auswahl formatieren von Absätzen.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Ruft das Drucken Rechteck für diese rich-Edit-Ansicht ab.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Ruft die Breite des drucken für diese rich-Edit-Ansicht ab.|  
|[CRichEditView:: GetRichEditCtrl](#getricheditctrl)|Ruft das rich-Edit-Steuerelement ab.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|Ruft das ausgewählte Element aus der rich-Edit-Ansicht ab.|  
|[CRichEditView::GetTextLength](#gettextlength)|Ruft die Länge des Texts in die rich-Edit-Ansicht ab.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Ruft die Anzahl der Zeichen oder Bytes in der rich-Edit-Ansicht ab. Erweiterte Flag-Liste für die Methode zum Bestimmen der Länge.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Fügt eine Datei als OLE-Element.|  
|[CRichEditView::InsertItem](#insertitem)|Fügt ein neues Element als OLE-Element.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Erfahren Sie, ob die Zwischenablage Daten in einem rich-Edit oder Text-Format enthält.|  
|[CRichEditView::OnCharEffect](#onchareffect)|Schaltet die für die aktuelle Auswahl formatieren von Zeichen.|  
|[CRichEditView::OnParaAlign](#onparaalign)|Ändert die Ausrichtung der Absätze.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Aktualisiert die Benutzeroberfläche für Öffentliche Memberfunktionen Zeichen.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Aktualisiert die Benutzeroberfläche für Öffentliche Memberfunktionen Absatz.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|Formatiert den angegebenen Text innerhalb des angegebenen Rechtecks.|  
|[CRichEditView::PrintPage](#printpage)|Formatiert den angegebenen Text innerhalb der angegebenen Seite.|  
|[CRichEditView::SetCharFormat](#setcharformat)|Legt die Attribute für die aktuelle Auswahl formatieren.|  
|[CRichEditView::SetMargins](#setmargins)|Legt die Ränder für diese umfassende Bearbeiten Ansicht.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Legt das Papierformat für diese rich-Edit-Ansicht fest.|  
|[CRichEditView::SetParaFormat](#setparaformat)|Legt die Attribute für die aktuelle Auswahl formatieren von Absätzen.|  
|[CRichEditView::TextNotFound](#textnotfound)|Setzt den internen Suche Zustand des Steuerelements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|Ruft ein Clipboard-Objekt für einen Bereich in dieser rich-Edit-Ansicht ab.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|Ruft ein Kontextmenü auf eine rechte Maustaste ab.|  
|[CRichEditView::IsSelected](#isselected)|Gibt an, ob das angegebene OLE-Element ausgewählt ist.|  
|[CRichEditView::OnFindNext](#onfindnext)|Sucht das nächste Vorkommen einer Teilzeichenfolge.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Aktualisiert eine Ansicht, die beim ersten an ein Dokument angefügt.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Systemeigene Daten von einem OLE-Element abgerufen.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Legt die Druckeigenschaften für das angegebene Gerät fest.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|Ersetzt alle Vorkommen einer angegebenen Zeichenfolge durch eine neue Zeichenfolge.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|Ersetzt die aktuelle Auswahl.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Verarbeitet die Benachrichtigung der Benutzer, der der angeforderten Text nicht gefunden wurde.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Fragt ab, über die Daten auf den `IDataObject`.|  
|[CRichEditView::WrapChanged](#wrapchanged)|Passt das Zielgerät für die Ausgabe für dieses Rich--Ansicht basierend auf den Wert des Edit `m_nWordWrap`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Gibt die Menge des Einzugs für Listen mit Aufzählungszeichen.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Gibt an, die Word-Wrap-Einschränkungen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text zugewiesen werden kann, Zeichen- und absatzformatierung und eingebettete OLE-Objekte enthalten kann. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle zum Formatieren von Text. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich Formatierungsvorgängen der Benutzer zur Verfügung stellen implementieren.  
  
 `CRichEditView`der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc`verwaltet die Liste der OLE-Client-Elemente, die in der Ansicht sind. `CRichEditCntrItem`Container-Seite Zugriff auf das Client-OLE-Element.  
  
 Diese Windows-Standardsteuerelement (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandte Klassen) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Ein Beispiel für eine rich-Edit-Ansicht in einer MFC-Anwendung verwenden, finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) -Beispiel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="adjustdialogposition"></a>CRichEditView::AdjustDialogPosition  
 Rufen Sie diese Funktion, um das angegebene Dialogfeld verschieben, sodass es nicht die aktuelle Auswahl verdeckt.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>Parameter  
 *pDlg*  
 Zeiger auf ein `CDialog` Objekt.  
  
##  <a name="canpaste"></a>CRichEditView::CanPaste  
 Rufen Sie diese Funktion, um zu bestimmen, ob die Zwischenablage Informationen enthält, die in dieser rich-Edit-Ansicht eingefügt werden kann.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zwischenablage Daten in einem Format enthält, diese rich-Edit-Ansicht annehmen kann; andernfalls 0.  
  
##  <a name="cricheditview"></a>CRichEditView::CRichEditView  
 Rufen Sie diese Funktion zum Erstellen einer `CRichEditView` Objekt.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>CRichEditView::DoPaste  
 Mit dieser Funktion können Sie das OLE-Element in fügen `dataobj` in die Rich-edit-Dokument/Ansicht.  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>Parameter  
 `dataobj`  
 Die [COleDataObject](../../mfc/reference/coledataobject-class.md) , fügen die Daten enthält.  
  
 `cf`  
 Das gewünschte Format der Zwischenablage.  
  
 `hMetaPict`  
 Die Metadatei, die das einzufügende Element darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion als Teil der Standardimplementierung des [QueryAcceptData](#queryacceptdata).  
  
 Diese Funktion bestimmt den Typ der basierend auf den Ergebnissen der Handler für Inhalte einfügen einfügen. Wenn `cf` 0 ist, das neue Element verwendet die aktuelle iconic-Darstellung. Wenn `cf` ungleich NULL ist und `hMetaPict` nicht **NULL**, verwendet das neue Element `hMetaPict` für seine Darstellung.  
  
##  <a name="findtext"></a>CRichEditView::FindText  
 Rufen Sie diese Funktion, um den angegebenen Text suchen und festlegen, dass die aktuelle Auswahl werden.  
  
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
 Gibt an, ob die Suche nur ganze Wörter nicht Teile von Wörtern übereinstimmen soll.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **TRUE**, die Suche am Ende des Puffers erfolgt. Wenn **FALSE**, die Suche am Anfang des Puffers erfolgt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `lpszFind` Text gefunden wird, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zeigt den Wartecursor während des Suchvorgangs.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#151;](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>CRichEditView::FindTextSimple  
 Rufen Sie diese Funktion, um den angegebenen Text suchen und festlegen, dass die aktuelle Auswahl werden.  
  
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
 Gibt an, ob die Suche nur ganze Wörter nicht Teile von Wörtern übereinstimmen soll.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **TRUE**, die Suche am Ende des Puffers erfolgt. Wenn **FALSE**, die Suche am Anfang des Puffers erfolgt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `lpszFind` Text gefunden wird, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="getcharformatselection"></a>CRichEditView::GetCharFormatSelection  
 Rufen Sie diese Funktion, um die Attribute der aktuellen Auswahl formatieren von Zeichen abzurufen.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Struktur, die die Attribute der aktuellen Auswahl formatieren von Zeichen enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) Nachricht und die [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>CRichEditView::GetClipboardData  
 Das Framework ruft diese Funktion als Teil der Verarbeitung von [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315).  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>Parameter  
 `lpchrg`  
 Zeiger auf die [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur der Bereich der Zeichen (und OLE-Elemente) auf dem angegebenen Datenobjekt kopieren `lplpdataobj`.  
  
 `dwReco`  
 Zwischenablage Vorgang Flag. Dabei kann es sich um einen der folgenden Werte sein.  
  
- **RECO_COPY** in die Zwischenablage kopieren.  
  
- **RECO_CUT** Ausschneiden in die Zwischenablage.  
  
- **RECO_DRAG** beim Ziehen (Drag & Drop).  
  
- **RECO_DROP** Drop-Vorgangs (Drag & Drop).  
  
- **RECO_PASTE** aus der Zwischenablage einfügen.  
  
 `lpRichDataObj`  
 Zeiger auf eine [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Objekt mit Daten aus der Zwischenablage aus der Rich-edit-Steuerelement ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 Zeiger auf die Zeigervariable, die Adresse des empfängt, die `IDataObject` -Objekt, das im angegebenen Bereich darstellt der `lpchrg` Parameter. Der Wert des `lplpdataobj` wird ignoriert, wenn ein Fehler zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert, der den Erfolg des Vorgangs meldet. Weitere Informationen zu `HRESULT`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert zeigt Erfolg an **IRichEditOleCallback::GetClipboardData** gibt die `IDataObject` zugegriffen `lplpdataobj`ist, andernfalls das Element zugegriffen wird `lpRichDataObj`. Überschreiben Sie diese Funktion, um eigene Zwischenablagedaten bereitstellen. Gibt die standardmäßige Implementierung dieser Funktion **E_NOTIMPL**.  
  
 Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] und [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) in der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="getcontextmenu"></a>CRichEditView::GetContextMenu  
 Das Framework ruft diese Funktion als Teil der Verarbeitung von [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317).  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>Parameter  
 *seltyp*  
 Der Typ der Markierung. Die Werte für die Auswahl werden im Abschnitt "Hinweise" beschrieben.  
  
 `lpoleobj`  
 Zeiger auf eine **Legend** -Struktur, die die erste ausgewählte OLE-Objekt angibt, wenn die Auswahl eines oder mehrerer OLE-Elemente enthält. Wenn der Bereich keine Elemente enthält `lpoleobj` ist **NULL**. Die **Legend** Struktur enthält einen Zeiger auf ein OLE-Objekt-vtable.  
  
 `lpchrg`  
 Zeiger auf eine [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) -Struktur, die die aktuelle Auswahl enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Behandeln Sie das Kontextmenü.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist eine übliche Teil des rechten Maustaste Verarbeitung.  
  
 Den Typ der Auswahl kann eine beliebige Kombination der folgenden Werte sein:  
  
- `SEL_EMPTY`Gibt an, dass keine aktuelle Auswahl vorhanden ist.  
  
- `SEL_TEXT`Gibt an, dass die aktuelle Auswahl Text enthält.  
  
- `SEL_OBJECT`Gibt an, dass die aktuelle Auswahl mindestens ein OLE-Element enthält.  
  
- `SEL_MULTICHAR`Gibt an, dass die aktuelle Auswahl mehrere Zeichen des Texts enthält.  
  
- `SEL_MULTIOBJECT`Gibt an, dass die aktuelle Auswahl mehr als ein OLE-Objekt enthält.  
  
 Die standardmäßige Implementierung gibt **NULL**. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu den **Legend** finden Sie unter OLE-Datenstrukturen und Zuordnung der Prozessstatusstruktur Artikel in der *OLE-Wissensdatenbank*.  
  
##  <a name="getdocument"></a>CRichEditView::GetDocument  
 Mit dieser Funktion können Sie einen Zeiger auf die `CRichEditDoc` dieser Ansicht zugeordnet.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) zugeordnete Objekt der `CRichEditView` Objekt.  
  
##  <a name="getinplaceactiveitem"></a>CRichEditView::GetInPlaceActiveItem  
 Aufruf dieser Funktion zum Abrufen des OLE Element, das derzeit aktiviert ist, an Stelle in diesem `CRichEditView` Objekt.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen, direkte aktive [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt in dieser rich-Edit-Ansicht; **NULL** liegt kein OLE-Element zurzeit im aktiven Zustand an.  
  
##  <a name="getmargins"></a>CRichEditView::GetMargins  
 Rufen Sie diese Funktion zum Abrufen der aktuellen Ränder beim Drucken verwendet.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ränder verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
##  <a name="getpagerect"></a>CRichEditView::GetPageRect  
 Rufen Sie diese Funktion, um die Dimensionen der drucken verwendete Seite zu erhalten.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Grenzen der Seite verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert basiert auf das Papierformat.  
  
##  <a name="getpapersize"></a>CRichEditView::GetPaperSize  
 Rufen Sie diese Funktion, um die aktuelle Papiergröße abzurufen.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Papiergröße verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#153;](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>CRichEditView::GetParaFormatSelection  
 Rufen Sie diese Funktion, um die Attribute der aktuellen Auswahl formatieren von Absätzen abgerufen.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Struktur, die die Attribute der aktuellen Auswahl formatieren von Absätzen enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) Nachricht und [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getprintrect"></a>CRichEditView::GetPrintRect  
 Rufen Sie diese Funktion, um die Grenzen des Druckbereichs innerhalb des Rechtecks Seite abrufen.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Grenzen des Bildbereichs verwendet beim Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#154;](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>CRichEditView::GetPrintWidth  
 Rufen Sie diese Funktion, um die Breite des Druckbereichs zu ermitteln.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des Druckbereichs, gemessen in `MM_TWIPS`.  
  
##  <a name="getricheditctrl"></a>CRichEditView:: GetRichEditCtrl  
 Rufen Sie diese Funktion zum Abrufen der [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) zugeordnete Objekt der `CRichEditView` Objekt.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das `CRichEditCtrl` Objekt für diese Ansicht.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="getselecteditem"></a>CRichEditView::GetSelectedItem  
 Rufen Sie diese Funktion zum Abrufen von OLE-Element (ein `CRichEditCntrItem` Objekt) in das ausgewählte `CRichEditView` Objekt.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) ausgewählte Objekt in der `CRichEditView` Objekt. **NULL** , wenn kein Element in dieser Ansicht ausgewählt ist.  
  
##  <a name="gettextlength"></a>CRichEditView::GetTextLength  
 Rufen Sie diese Funktion zum Abrufen der Länge des Texts in diesem `CRichEditView` Objekt.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Texts in diesem `CRichEditView` Objekt.  
  
##  <a name="gettextlengthex"></a>CRichEditView::GetTextLengthEx  
 Rufen Sie diese Memberfunktion zum Berechnen der Länge des Texts in diesem `CRichEditView` Objekt.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Der Wert gibt die Methode zum Bestimmen der Länge verwendet werden. Dieser Member kann eine oder mehrere der Werte in Flags-Mitglied der [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) beschrieben, die der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `uCodePage`  
 Die Codepage für die Übersetzung (CP_ACP für ANSI-Codepage, 1200 für Unicode).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen oder Bytes in das Bearbeitungssteuerelement. Wenn nicht kompatible Flags, im festgelegt wurden `dwFlags`, diese Memberfunktion gibt `E_INVALIDARG`.  
  
### <a name="remarks"></a>Hinweise  
 `GetTextLengthEx`Stellt zusätzliche Methoden zum Bestimmen der Länge des Texts an. Die Funktionalität des Rich bearbeiten 2.0 unterstützt. Weitere Informationen finden Sie unter [zu Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="insertfileasobject"></a>CRichEditView::InsertFileAsObject  
 Rufen Sie diese Funktion zum Einfügen der angegebenen Datei (als ein [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt) in eine umfassende Ansicht bearbeiten.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge mit den Namen der Datei, die eingefügt werden soll.  
  
##  <a name="insertitem"></a>CRichEditView::InsertItem  
 Rufen Sie diese Funktion zum Einfügen einer [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt in eine rich-Edit-Ansicht.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Zeiger auf das Element eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert, der den Erfolg der Einfügemarke.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu `HRESULT`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isricheditformat"></a>CRichEditView::IsRichEditFormat  
 Rufen Sie diese Funktion, um festzustellen, ob `cf` ist ein Zwischenablageformat wird Text, rich-Text oder rich-Text mit OLE-Elementen.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 Das Format der Zwischenablage von Interesse sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `cf` ist eine umfassende Zwischenablageformat bearbeiten oder Text.  
  
##  <a name="isselected"></a>CRichEditView::IsSelected  
 Rufen Sie diese Funktion, um zu bestimmen, ob das angegebene OLE-Element in dieser Ansicht markiert ist.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDocItem`  
 Ein Zeiger auf ein Objekt in der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt ausgewählt ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn die abgeleiteten Ansichtsklasse eine andere Methode für die Behandlung der Auswahl von OLE-Elementen verfügt.  
  
##  <a name="m_nbulletindent"></a>CRichEditView::m_nBulletIndent  
 Die Einzüge für Aufzählungszeichen in einer Liste in der Standardeinstellung, 720 Einheiten, 1/2 Zoll.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>CRichEditView::m_nWordWrap  
 Gibt den Typ des Zeilenumbruchs für diese rich-Edit-Ansicht an.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Hinweise  
 Einer der folgenden Werte:  
  
- `WrapNone`Gibt keine automatischen Zeilenumbruch an.  
  
- `WrapToWindow`Gibt an, basierend auf der Breite des Fensters bestimmt.  
  
- `WrapToTargetDevice`Gibt an, basierend auf den Merkmalen des Zielgeräts Zeilenumbruch.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::WrapChanged](#wrapchanged).  
  
##  <a name="onchareffect"></a>CRichEditView::OnCharEffect  
 Rufen Sie diese Funktion, um die Effekte der aktuellen Auswahl formatieren von Zeichen zu wechseln.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMask`  
 Zeichenformate Effekte, die aktuelle Auswahl zu ändern.  
  
 `dwEffect`  
 Die gewünschte Liste Zeichenformat Effekte aktivieren bzw. deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Aufruf dieser Funktion schaltet die Effekte der angegebenen Formatierung für die aktuelle Auswahl.  
  
 Weitere Informationen zu den `dwMask` und `dwEffect` Parameter und der möglichen Werte finden Sie unter der entsprechenden Datenmember [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#155;](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>CRichEditView::OnFindNext  
 Vom Framework aufgerufen, bei der Verarbeitung von Befehlen über das Dialogfeld Suchen und ersetzen.  
  
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
 Die Richtung zu suchen: **TRUE** angibt. **FALSE**, up.  
  
 `bCase`  
 Gibt an, ob die Suche Groß-/Kleinschreibung beachtet werden soll.  
  
 `bWord`  
 Gibt an, ob die Suche nur ganze Wörter zu suchen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Suchen von Text in der `CRichEditView`. Überschreiben Sie diese Funktion, um die Suchkriterien für die Klasse abgeleitete Sicht ändern.  
  
##  <a name="oninitialupdate"></a>CRichEditView::OnInitialUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber vor dem Beginn der Ansicht angezeigt wird.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) Memberfunktion ohne Hinweis Informationen (d. h. unter Verwendung der Standardwerte von 0 für die `lHint` Parameter und **NULL** für die `pHint` Parameter). Überschreiben Sie diese Funktion, um die einmalige Initialisierung ausführen, die Informationen über das Dokument erforderlich ist. Beispielsweise verfügt die Anwendung Dokumente mit fester Größe, können dieser Funktion Sie eine Ansicht Bildlauf Grenzen basierend auf der Dokumentgröße zu initialisieren. Wenn Ihre Anwendung variabler Dokumente unterstützt, verwenden Sie `OnUpdate` zum Aktualisieren der Bildlauf schränkt jedes Mal das Dokument ändert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::m_nWordWrap](#m_nwordwrap).  
  
##  <a name="onpastenativeobject"></a>CRichEditView::OnPasteNativeObject  
 Verwenden Sie diese Funktion zum Laden von systemeigener Daten von einem eingebetteten Element.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>Parameter  
 *lpStg*  
 Zeiger auf eine [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; Andernfalls wird 0;  
  
### <a name="remarks"></a>Hinweise  
 Sie würden dies wird normalerweise durch das Erstellen einer [COleStreamFile](../../mfc/reference/colestreamfile-class.md) rund um die `IStorage`. Die `COleStreamFile` angefügt werden können, um ein Archiv und [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) aufgerufen, um die Daten zu laden.  
  
 Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onparaalign"></a>CRichEditView::OnParaAlign  
 Rufen Sie diese Funktion zum Ändern der Ausrichtung Absatz für die ausgewählten Absätze.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>Parameter  
 `wAlign`  
 Die gewünschte Ausrichtung von Absätzen. Einer der folgenden Werte:  
  
- `PFA_LEFT`Richten Sie die Absätze werden am linken Rand aus.  
  
- `PFA_RIGHT`Richten Sie die Absätze am rechten Rand an.  
  
- `PFA_CENTER`Zentrieren Sie die Absätze zwischen den Rändern.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#156;](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>CRichEditView::OnPrinterChanged  
 Überschreiben Sie diese Funktion zum Ändern der Eigenschaften für diese rich-Edit-Ansicht eine Änderung des Druckers.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>Parameter  
 `dcPrinter`  
 Ein [CDC](../../mfc/reference/cdc-class.md) Objekt für den neuen Drucker.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung wird das Papierformat auf die physische Höhe und Breite für das Ausgabegerät (Drucker). Liegt keine Gerätekontext zugeordnet `dcPrinter`, die standardmäßige Implementierung legt das Papierformat 8,5 x 11 Zoll.  
  
##  <a name="onreplaceall"></a>CRichEditView::OnReplaceAll  
 Vom Framework aufgerufen, bei der Verarbeitung von ersetzen alle Befehle aus dem Dialogfeld ersetzen.  
  
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
 Gibt an, ob die Suche ganze Wörter auswählen muss.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um alle Vorkommen des angegebenen Text durch eine andere Zeichenfolge ersetzen. Überschreiben Sie diese Funktion, um die Suchkriterien für diese Ansicht ändern.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="onreplacesel"></a>CRichEditView::OnReplaceSel  
 Vom Framework aufgerufen, bei der Verarbeitung von ersetzen Befehle über das Dialogfeld ersetzen.  
  
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
 Gibt die Richtung der Suche: **TRUE** ist. **FALSE**, up.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.  
  
 `bWord`  
 Gibt an, ob die Suche ganze Wörter auswählen muss.  
  
 `lpszReplace`  
 Der Ersetzungstext.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um ein Vorkommen des angegebenen Text durch eine andere Zeichenfolge ersetzen. Überschreiben Sie diese Funktion, um die Suchkriterien für diese Ansicht ändern.  
  
##  <a name="ontextnotfound"></a>CRichEditView::OnTextNotFound  
 Vom Framework aufgerufen, wenn eine Suche fehl.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text, der nicht gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Ändern der Ausgabe-benachrichtigungs aus einer [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356).  
  
 Weitere Informationen finden Sie unter [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#157;](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>CRichEditView::OnUpdateCharEffect  
 Das Framework ruft diese Funktion, um die Befehlsbenutzeroberfläche für Zeichen Effekt Befehle zu aktualisieren.  
  
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
 Gibt das Zeichen Formatierung wirksam.  
  
### <a name="remarks"></a>Hinweise  
 Die Maske `dwMask` gibt an, welches Formatierungsattribute überprüfen Zeichen. Die Flags `dwEffect` Liste Zeichenformate Attribute Set/löschen.  
  
 Weitere Informationen zu den `dwMask` und `dwEffect` Parameter und der möglichen Werte finden Sie unter der entsprechenden Datenmember [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#158;](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>CRichEditView::OnUpdateParaAlign  
 Das Framework ruft diese Funktion, um die Befehlsbenutzeroberfläche Absatz Effekt Befehle zu aktualisieren.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt.  
  
 `wAlign`  
 Die Ausrichtung von Absätzen zu überprüfen. Einer der folgenden Werte:  
  
- `PFA_LEFT`Richten Sie die Absätze werden am linken Rand aus.  
  
- `PFA_RIGHT`Richten Sie die Absätze am rechten Rand an.  
  
- `PFA_CENTER`Zentrieren Sie die Absätze zwischen den Rändern.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#159;](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>CRichEditView::PrintInsideRect  
 Mit dieser Funktion können Sie einen Bereich von Text in einem rich-Edit-Steuerelement in passen formatieren *RectLayout* für das Gerät mit dem angegebenen `pDC`.  
  
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
 Ein Zeiger auf einen Gerätekontext für den Ausgabebereich.  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Ausgabebereich definiert.  
  
 `nIndexStart`  
 Nullbasierte Index des ersten Zeichens formatiert werden.  
  
 `nIndexStop`  
 Nullbasierte Index des letzten Zeichens formatiert werden.  
  
 *bOutput*  
 Gibt an, ob der Text gerendert werden soll. Wenn **FALSE**, der Text wird nur gemessen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Zeichens, die in den Ausgabebereich plus&1; entspricht.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel folgt diesem Aufruf durch einen Aufruf von [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) die Ausgabe generiert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="printpage"></a>CRichEditView::PrintPage  
 Mit dieser Funktion können Sie einen Bereich von Text in einem rich-Edit-Steuerelement für das Ausgabegerät angegebenen format `pDC`.  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf einen Gerätekontext für Seite ausgegeben.  
  
 `nIndexStart`  
 Nullbasierte Index des ersten Zeichens formatiert werden.  
  
 `nIndexStop`  
 Nullbasierte Index des letzten Zeichens formatiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Zeichens, das auf der Seite plus&1; entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Das Layout der einzelnen Seiten wird gesteuert, indem [GetPageRect](#getpagerect) und [GetPrintRect](#getprintrect). In der Regel folgt diesem Aufruf durch einen Aufruf von [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) die Ausgabe generiert.  
  
 Beachten Sie, dass Ränder relativ zur physischen Seite, nicht die logische Seite. Ränder&0; (null) werden daher oft den Text clip, da viele Drucker nicht bedruckbaren Bereiche auf der Seite haben. Um zu vermeiden, kürzen den Text, rufen Sie [SetMargins](#setmargins) und legen Sie angemessene vor dem Drucken.  
  
##  <a name="queryacceptdata"></a>CRichEditView::QueryAcceptData  
 Vom Framework aufgerufen wird, ein Objekt in die rich-Edit einzufügen.  
  
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
 Zeiger auf die [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Abfrage.  
  
 *lpcfFormat*  
 Ein Zeiger auf das zulässige Format.  
  
 `dwReco`  
 Nicht verwendet.  
  
 *bReally*  
 Gibt an, ob der Einfügevorgang werden oder nicht fortgesetzt soll.  
  
 `hMetaFile`  
 Ein Handle für die Metadatei, die zum Zeichnen des Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert, der den Erfolg des Vorgangs meldet.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um andere Organisation der COM-Elemente im abgeleiteten Dokumentklasse behandeln. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen zu `HRESULT` und `IDataObject`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) und [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)bzw. in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#160;](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>CRichEditView::SetCharFormat  
 Mit dieser Funktion können Sie die Formatierungsattribute für den neuen Text in diesem Zeichensatz `CRichEditView` Objekt.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die das neue Standardzeichen Formatierungsattribute enthält.  
  
### <a name="remarks"></a>Hinweise  
 Nur die angegebenen Attribute der **DwMask** Mitglied `cf` dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) Nachricht und [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>CRichEditView::SetMargins  
 Rufen Sie diese Funktion, um Druckränder für diese rich-Edit-Ansicht festgelegt.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>Parameter  
 *rectMargin*  
 Die neue Werte für Ränder für das Drucken, gemessen in `MM_TWIPS`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [m_nWordWrap an](#m_nwordwrap) ist `WrapToTargetDevice`, rufen Sie [WrapChanged](#wrapchanged) nach der Verwendung dieser Funktion Druckeigenschaften anpassen.  
  
 Beachten Sie, dass die Ränder von [PrintPage](#printpage) sind relativ zum physischen Seite, nicht die logische Seite. Ränder&0; (null) werden daher oft den Text clip, da viele Drucker nicht bedruckbaren Bereiche auf der Seite haben. Um zu vermeiden, kürzen den Text, rufen Sie mit `SetMargins` angemessenen Drucker Ränder vor dem Drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="setpapersize"></a>CRichEditView::SetPaperSize  
 Rufen Sie diese Funktion, um das Papierformat zum Drucken dieser rich-Edit-Ansicht festzulegen.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>Parameter  
 *sizePaper*  
 Die neuen Werte der Dokument-Größe für den Druck, gemessen in `MM_TWIPS`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [m_nWordWrap an](#m_nwordwrap) ist `WrapToTargetDevice`, rufen Sie [WrapChanged](#wrapchanged) nach der Verwendung dieser Funktion Druckeigenschaften anpassen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#161;](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditView::SetParaFormat  
 Rufen Sie diese Funktion zum Festlegen des Formatierungsattribute für die aktuelle Auswahl in diesem Absatzes `CRichEditView` Objekt.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Parameter  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur, enthält den neuen Standard Absatz Formatierungsattribute.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die angegebenen Attribute der **DwMask** Mitglied `pf` dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) Nachricht und [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#162;](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>CRichEditView::TextNotFound  
 Mit dieser Funktion können Sie den internen Suche Status zurücksetzen der [CRichEditView](../../mfc/reference/cricheditview-class.md) Steuerelement nach einem fehlgeschlagenen Aufruf von [FindText](#findtext).  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Enthält die Zeichenfolge, die nicht gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, diese Methode aufgerufen werden, sofort nach der fehlgeschlagene Aufrufe von [FindText](#findtext) , damit die interne Suche Zustand des Steuerelements ordnungsgemäß zurückgesetzt wird.  
  
 Die `lpszFind` -Parameter muss den gleichen Inhalt wie die bereitgestellte Zeichenfolge enthalten [FindText](#findtext). Nach dem Zurücksetzen des Status interner suchen, diese Methode aufrufen, wird die [OnTextNotFound](#ontextnotfound) Methode mit der angegebenen Suchzeichenfolge.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::FindText](#findtext).  
  
##  <a name="wrapchanged"></a>CRichEditView::WrapChanged  
 Rufen Sie diese Funktion, wenn die Druckeigenschaften geändert haben ( [SetMargins](#setmargins) oder [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, die so zu ändern, das Rich--Ansicht Edit auf Änderungen in reagiert [m_nWordWrap an](#m_nwordwrap) oder die Druckeigenschaften ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#163;](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)

