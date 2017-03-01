---
title: CView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CView
dev_langs:
- C++
helpviewer_keywords:
- views [C++], view classes
- multiple views
- CView class
- document/view architecture
- input, and view class
- MDI [C++], view windows
- print preview, view windows
- windows [C++], views
- child windows, views
- frame windows [C++], views
- user input [C++], interpreting through view class
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ce5100a9ee4a1c20df04f79f0c8cd645ae3afce7
ms.lasthandoff: 02/24/2017

---
# <a name="cview-class"></a>CView-Klasse
Stellt die grundlegende Funktionalität für benutzerdefinierte Ansichtsklassen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CView::CView](#cview)|Erstellt ein `CView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CView::DoPreparePrinting](#doprepareprinting)|Zeigt das Dialogfeld Drucken und Drucker-Gerätekontext erstellt. Beim Überschreiben von Aufrufen der `OnPreparePrinting` Member-Funktion.|  
|[CView::GetDocument](#getdocument)|Gibt das Dokument mit der Ansicht.|  
|[CView::IsSelected](#isselected)|Testet, ob ein Dokument oder ein Element ausgewählt ist. Für OLE-Unterstützung erforderlich.|  
|[CView::OnDragEnter](#ondragenter)|Wird aufgerufen, wenn ein Element zunächst in den Drag & Drop-Bereich einer Ansicht gezogen wird.|  
|[CView::OnDragLeave](#ondragleave)|Wird aufgerufen, wenn ein gezogenes Element bewirkt, die Drag & Drop-Bereich einer Ansicht dass.|  
|[CView::OnDragOver](#ondragover)|Wird aufgerufen, wenn ein Element über den Drag & Drop-Bereich einer Ansicht gezogen wird.|  
|[CView::OnDragScroll](#ondragscroll)|Wird aufgerufen, um festzustellen, ob der Cursor in der Bildlaufbereich des Fensters gezogen wird.|  
|[CView::OnDrop](#ondrop)|Wird aufgerufen, wenn ein Element in den Drag & Drop-Bereich einer Ansicht Standardhandler gelöscht wurde.|  
|[CView::OnDropEx](#ondropex)|Wird aufgerufen, wenn ein Element in den Bereich ziehen und Ablegen einer Sicht, primäre Ereignishandler gelöscht wurde.|  
|[CView:: OnInitialUpdate](#oninitialupdate)|Wird aufgerufen, nachdem eine Ansicht in ein Dokument angefügt ist.|  
|[CView::OnPrepareDC](#onpreparedc)|Aufgerufen, bevor die `OnDraw` Member-Funktion wird aufgerufen, für die Bildschirmanzeige oder der `OnPrint` Member-Funktion für Druck oder den Seitenansichtmodus aufgerufen wird.|  
|[CView::OnScroll](#onscroll)|Wird aufgerufen, wenn OLE-Elementen, über den Rand der Ansicht gezogen werden.|  
|[CView::OnScrollBy](#onscrollby)|Wird aufgerufen, wenn eine Ansicht, die aktive in direkten OLE-Elementen ein Bildlauf durchgeführt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|Wird aufgerufen, wenn das Rahmenfenster, das die Sicht aktiviert oder deaktiviert wird.|  
|[CView::OnActivateView](#onactivateview)|Wird aufgerufen, wenn eine Ansicht aktiviert wird.|  
|[CView::OnBeginPrinting](#onbeginprinting)|Aufgerufen, wenn ein Auftrag beginnt. Überschreiben Sie, um die Graphics Device Interface (GDI) Ressourcen zuteilen.|  
|[CView:: OnDraw](#ondraw)|Wird aufgerufen, um ein Bild des Dokuments für den Bildschirm anzeigen, drucken oder Seitenansicht zu rendern. Die Implementierung erforderlich sind.|  
|[CView::OnEndPrinting](#onendprinting)|Wird aufgerufen, wenn ein Druckauftrag beendet; außer Kraft setzen, um GDI-Ressourcen freizugeben.|  
|[CView::OnEndPrintPreview](#onendprintpreview)|Wird aufgerufen, wenn im Vorschaumodus beendet wird.|  
|[CView::OnPreparePrinting](#onprepareprinting)|Aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau angezeigt wird. Überschreiben Sie, um das Dialogfeld Drucken zu initialisieren.|  
|[CView::OnPrint](#onprint)|Zum Drucken oder die Vorschau einer Seite des Dokuments aufgerufen.|  
|[CView::OnUpdate](#onupdate)|Wird aufgerufen, um eine Ansicht zu informieren, die das Dokument wurde geändert.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Ansicht ist an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und der Benutzer: die Ansicht stellt ein Bild des Dokuments auf dem Bildschirm oder Drucker und Benutzereingaben als Vorgängen des Dokuments interpretiert.  
  
 Eine Ansicht ist ein untergeordnetes Element eines Rahmenfensters. Mehrere Ansichten kann einem Rahmenfenster, wie im Fall eines unterteilten Fensters freigeben. Die Beziehung zwischen einer Ansichtsklasse ein Rahmenfenster (Klasse) und einer Dokumentklasse wird eingerichtet, indem ein `CDocTemplate` Objekt. Wenn der Benutzer öffnet ein neues Fenster oder eine vorhandene teilt eine das Framework eine neue Ansicht erstellt und an das Dokument angefügt.  
  
 Eine Sicht kann nur ein Dokument angefügt werden, aber ein Dokument kann mehrere Sichten gleichzeitig angefügt haben – beispielsweise, wenn das Dokument in ein oder mehrere untergeordnete Fenster in einer Anwendung für multiple Document Interface (MDI) angezeigt wird. Ihre Anwendung kann verschiedene Arten von Ansichten für einen bestimmten Dokumenttyp unterstützen; Beispielsweise kann ein Textverarbeitungsprogramm bereitstellen, eine Ansicht der vollständige Text eines Dokuments und eine Gliederungsansicht, die nur die Abschnittsüberschriften anzeigt. Diese verschiedenen Typen von Ansichten können in getrennten Rahmenfenstern oder in separaten Bereichen eines einzelnen Frame-Fensters platziert werden, wenn Sie ein unterteiltes Fenster verwenden.  
  
 Eine Ansicht möglicherweise für die Behandlung von mehreren verschiedenen Arten von Eingaben, z. B. Tastatureingaben, Mauseingaben oder Eingabe per Drag & Drop sowie Befehle aus Menüs, Symbolleisten und Bildlaufleisten verantwortlich. Eine Ansicht erhält die Befehle, die durch das Rahmenfenster weitergeleitet. Wenn die Ansicht keinen bestimmten Befehl verarbeitet, wird den Befehl an das zugeordnete Dokument weitergeleitet. Wie alle Befehlsziele behandelt eine Ansicht Nachrichten über eine Zuordnung für die Nachricht.  
  
 Die Ansicht ist verantwortlich für das Anzeigen und ändern die Daten des Dokuments jedoch nicht für die Speicherung. Das Dokument enthält die Ansicht mit den erforderlichen Details zu den Daten. Sie können den Zugriff anzeigen lassen, den direkt die Datenmember des Dokuments ein, oder Sie Memberfunktionen in der für die Ansichtsklasse aufrufen bereitstellen können.  
  
 Wenn Daten eines Dokuments geändert wird, ruft die Ansicht, die verantwortlich für die Änderungen in der Regel die [UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) -Funktion für das Dokument, das durch Aufrufen die weiteren Ansichten benachrichtigt die `OnUpdate` für jeden Member-Funktion. Die standardmäßige Implementierung des `OnUpdate` wird die Ansicht des gesamten Clientbereich ungültig. Sie können überschreiben, um nur die Bereiche des Clientbereich für ungültig zu erklären, die den geänderten Bereichen des Dokuments zugeordnet.  
  
 Mit `CView`, eine Klasse ableiten und implementieren die `OnDraw` Memberfunktion Bildschirmanzeige ausführen. Sie können auch `OnDraw` drucken und Druckvorschau ausführen. Das Framework ist die Druckschleife zum Drucken und Vorschau des Dokuments.  
  
 Eine Ansicht verarbeitet Bildlaufleisten-Nachrichten mit den [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen. Sie können die Bildlaufleiste Meldungsbehandlung in diesen Funktionen implementieren, oder Sie können die `CView` abgeleitete Klasse [CScrollView](../../mfc/reference/cscrollview-class.md) Bildlauf für Sie behandeln.  
  
 Neben `CScrollView`, die Microsoft Foundation Class-Bibliothek bietet neun von abgeleiteten Klassen `CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md), eine Sicht, die die Verwendung von Dokument - Architektur mit Struktur, Liste und Rich-edit-Steuerelemente anzeigen.  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), eine Sicht, die Datenbankdatensätze in Dialogfeld-Steuerelemente anzeigt.  
  
- [CEditView](../../mfc/reference/ceditview-class.md), eine Sicht, die einen einfachen mehrzeiliger Text-Editor bereitstellt. Sie können ein `CEditView` Objekt als ein Steuerelement in einem Dialogfeld sowie eine Ansicht in einem Dokument.  
  
- [CFormView](../../mfc/reference/cformview-class.md), eine bildlauffähige Ansicht, die Dialogfeld-Steuerelemente enthält und basiert auf einer Dialogfeldvorlagen-Ressource.  
  
- [CListView](../../mfc/reference/clistview-class.md), eine Sicht, die Verwendung von Dokument - View-Architektur mit Steuerelementen ermöglicht.  
  
- [CRecordView](../../mfc/reference/crecordview-class.md), eine Sicht, die Datenbankdatensätze in Dialogfeld-Steuerelemente anzeigt.  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md), eine Sicht, die die Verwendung von Dokument - Architektur mit Rich-edit-Steuerelemente anzeigen.  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md), eine Ansicht, die automatisch Bildlauf unterstützt.  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md), eine Sicht, die Verwendung von Dokument - View-Architektur mit Strukturansicht-Steuerelementen ermöglicht.  
  
 Die `CView` -Klasse verfügt auch über eine abgeleitete Implementierung-Klasse namens **CPreviewView**, der Seitenansicht Ausführen von das Framework verwendet wird. Diese Klasse bietet Unterstützung für die Funktionen im Seitenansichtsfenster wie z. B. eine Symbolleiste oder Double Seite Vorschau und Zoom wird, die das angezeigte Bild vergrößern. Sie müssen aufrufen oder Überschreiben eines **CPreviewView**Memberfunktionen, es sei denn, Sie möchten Ihre eigene Schnittstelle für die Seitenansicht implementieren (z. B. wenn im Seitenansichtsmodus bearbeiten unterstützt werden sollen). Weitere Informationen zur Verwendung von `CView`, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [Drucken](../../mfc/printing.md). Darüber hinaus finden Sie unter [Technische Hinweis 30](../../mfc/tn030-customizing-printing-and-print-preview.md) ausführliche Informationen zum Anpassen der Seitenansicht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecviewa--cviewcview"></a><a name="cview"></a>CView::CView  
 Erstellt ein `CView`-Objekt.  
  
```  
CView();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft der Konstruktor auf, wenn ein neues Rahmenfenster erstellt wird, oder Teilen Sie ein Fenster ist. Überschreiben Sie die [OnInitialUpdate](#oninitialupdate) Member-Funktion, um die Ansicht zu initialisieren, nachdem das Dokument zugeordnet ist.  
  
##  <a name="a-namedoprepareprintinga--cviewdoprepareprinting"></a><a name="doprepareprinting"></a>CView::DoPreparePrinting  
 Rufen Sie diese Funktion aus der Überschreibung der [OnPreparePrinting](#onprepareprinting) das Dialogfeld "Drucken" aufrufen, und erstellen einen Drucker-Gerätekontext.  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Druck oder den Seitenansichtmodus beginnen kann; 0, wenn der Vorgang abgebrochen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Funktion hängt davon, ob es für Druck oder den Seitenansichtmodus aufgerufen wird (angegeben durch die **M_bPreview** Mitglied der `pInfo` Parameter). Wenn eine Datei gedruckt wird, ruft diese Funktion im Dialogfeld Drucken unter Verwendung der Werte in der [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Datenstruktur, `pInfo` zeigt auf, nachdem der Benutzer das Dialogfeld geschlossen wurde, erstellt die Funktion anhand der Einstellungen der Benutzer im Dialogfeld angegeben und gibt diesen Gerätekontext über Drucker-Gerätekontext der `pInfo` Parameter. Gerätekontext wird verwendet, um das Dokument zu drucken.  
  
 Wenn eine Datei in der Vorschau ist, erstellt diese Funktion einen Drucker-Gerätekontext mithilfe der aktuellen Druckereinstellungen. Gerätekontext dient zur Simulation des Druckers in der Vorschau.  
  
##  <a name="a-namegetdocumenta--cviewgetdocument"></a><a name="getdocument"></a>CView::GetDocument  
 Rufen Sie diese Funktion, um einen Zeiger auf die Ansicht Dokument abzurufen.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CDocument](../../mfc/reference/cdocument-class.md) der Ansicht zugeordnete Objekt. **NULL** , wenn die Ansicht nicht an ein Dokument angefügt ist.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch können Sie das Dokument Memberfunktionen aufrufen.  
  
##  <a name="a-nameisselecteda--cviewisselected"></a><a name="isselected"></a>CView::IsSelected  
 Vom Framework aufgerufen wird, überprüfen Sie, ob das angegebene Dokumentelement ausgewählt ist.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDocItem`  
 Verweist auf das Dokumentelement getestet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Dokumentelement aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die standardmäßige Implementierung dieser Funktion **FALSE**. Überschreiben Sie diese Funktion, wenn Sie mit der Auswahl implementieren [CDocItem](../../mfc/reference/cdocitem-class.md) Objekte. Wenn die Ansicht OLE-Elemente enthält, müssen Sie diese Funktion überschreiben.  
  
##  <a name="a-nameonactivateframea--cviewonactivateframe"></a><a name="onactivateframe"></a>CView::OnActivateFrame  
 Wird vom Framework aufgerufen, wenn das Rahmenfenster, das die Sicht aktiviert oder deaktiviert wird.  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `nState`  
 Gibt an, ob das Rahmenfenster ist aktiviert oder deaktiviert. Die folgenden Werte sind möglich:  
  
- **WA_INACTIVE** Rahmenfenster wird deaktiviert.  
  
- **WA_ACTIVE** Rahmenfenster anderen als einen Mausklick (z. B. durch Verwendung der Tastaturschnittstelle des Fensters auswählen) mithilfe einer bestimmten Methode aktiviert wird.  
  
- **WA_CLICKACTIVE** Rahmenfenster durch einen Mausklick aktiviert wird  
  
 `pFrameWnd`  
 Ein Zeiger auf das Rahmenfenster, das aktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion auf, wenn auszuführenden besondere Verarbeitung durch, wenn das Rahmenfenster der Sicht zugeordneten aktiviert oder deaktiviert wird. Beispielsweise [CFormView](../../mfc/reference/cformview-class.md) Außerkraftsetzung führt, wenn speichert, und stellt das Steuerelement, das Fokus besitzt.  
  
##  <a name="a-nameonactivateviewa--cviewonactivateview"></a><a name="onactivateview"></a>CView::OnActivateView  
 Wird vom Framework aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert wird.  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>Parameter  
 `bActivate`  
 Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  
  
 `pActivateView`  
 Verweist auf das View-Objekt, das aktiviert wird.  
  
 `pDeactiveView`  
 Verweist auf das View-Objekt, das deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion setzt den Fokus auf die Ansicht aktiviert wird. Überschreiben Sie diese Funktion, wenn auszuführenden besonderer Verarbeitung, wenn eine Ansicht aktiviert oder deaktiviert wird. Z. B. Wenn Sie besondere visuelle Hinweise bereitstellen, die die aktive Ansicht von inaktiven Ansichten unterscheiden möchten, Sie würden Untersuchen der `bActivate` Parameter und die Ansicht Darstellung entsprechend aktualisieren.  
  
 Die `pActivateView` und `pDeactiveView` Parameter zeigen Sie auf die gleiche Ansicht, wenn die Anwendung Hauptrahmenfenster ohne Änderung in der aktiven Ansicht aktiviert ist – beispielsweise, wenn der Fokus aus einer anderen Anwendung mit diesem, anstatt von einer Ansicht zu einem anderen in der Anwendung oder übertragen wird, wenn von untergeordneten MDI-Fenstern gewechselt. Dies ermöglicht eine Ansicht, um die Palette erneut zu erkennen, bei Bedarf.  
  
 Diese Parameter unterscheiden sich bei der [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) aufgerufen wird und eine Ansicht, die von Was unterscheidet [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) zurück. Dies geschieht am häufigsten bei Splitterfenster.  
  
##  <a name="a-nameonbeginprintinga--cviewonbeginprinting"></a><a name="onbeginprinting"></a>CView::OnBeginPrinting  
 Wird zu Beginn eines Druckauftrags oder Seitenansichtauftrags vom Framework aufgerufen, nachdem `OnPreparePrinting` aufgerufen wurde.  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um alle speziell für den Druck benötigten GDI-Ressourcen, z. B. Stifte oder Schriftarten, zuzuordnen. Wählen Sie die GDI-Objekte im Gerätekontext innerhalb der [OnPrint](#onprint) Member-Funktion für jede Seite, die sie verwendet. Wenn Sie das gleiche Ansichtsobjekt verwenden, um den Bildschirm anzuzeigen und zu drucken, verwenden Sie separate Variablen für die für jeden Bildschirm erforderlichen GDI-Ressourcen. Dadurch können Sie den Bildschirm während des Druckens aktualisieren.  
  
 Mit dieser Funktion können Sie auch Initialisierungen durchführen, die von Eigenschaften des Druckergerätekontextes abhängig sind. Beispielsweise kann die Anzahl der Seiten, die zum Drucken des Dokuments benötigt werden, von den Einstellungen abhängig sein, die der Benutzer im Dialogfeld „Drucken“ (z. B. Seitenlänge) angibt. In einem solchen Fall müssen Sie die Länge des Dokuments in angeben können nicht der [OnPreparePrinting](#onprepareprinting) -Memberfunktion, in denen Sie würden normalerweise dazu, Sie müssen warten, bis der Drucker-Gerätekontext basierend auf den Einstellungen des Dialogfelds erstellt wurde. [OnBeginPrinting](#onbeginprinting) ist die erste überschreibbare Funktion, die Ihnen sofortigen Zugriff auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, das den Druckergerätekontext darstellt, daher können Sie die Länge des Dokuments von dieser Funktion festlegen. Wenn die Länge des Dokuments nicht zu diesem Zeitpunkt angegeben wird, wird in der Seitenansicht keine Bildlaufleiste angezeigt.  
  
##  <a name="a-nameondragentera--cviewondragenter"></a><a name="ondragenter"></a>CView::OnDragEnter  
 Vom Framework aufgerufen, wenn der Mauszeiger den Bereich ohne Bildlauf des im Zielfenster zuerst eintritt.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) in der Dropdown-Bereich der Ansicht gezogen wird.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT` Enumerationstyps, der den Typ der Dropdownliste, die auftreten können anzeigt, wenn der Benutzer das Objekt an dieser Position gelöscht. Die Dropdownliste in der Regel richtet sich nach der aktuellen Tastenzustand erkennbar `dwKeyState`. Eine standardmäßige Zuordnung von Keystates zu `DROPEFFECT` Werte sind:  
  
- `DROPEFFECT_NONE`Das Objekt kann nicht in diesem Fenster gelöscht werden.  
  
- `DROPEFFECT_LINK`für **MK_CONTROL | MK_SHIFT** erstellt eine Verknüpfung zwischen dem Objekt und dem Server.  
  
- `DROPEFFECT_COPY`für **MK_CONTROL** erstellt eine Kopie des gelöschten Objekts.  
  
- `DROPEFFECT_MOVE`für **MK_ALT** erstellt eine Kopie des gelöschten Objekts und löschen Sie das ursprüngliche Objekt. Dies ist normalerweise die Standard-Drop-Effekt, die Ansicht dieses Datenobjekt annehmen kann.  
  
 Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Hinweise  
 Standardimplementierung besteht darin, nichts zurückzugeben, und wählen Sie `DROPEFFECT_NONE`.  
  
 Überschreiben Sie diese Funktion in Vorbereitung auf zukünftige Aufrufe an die [OnDragOver](#ondragover) Member-Funktion. Aus dem Datenobjekt erforderlichen Daten abgerufen werden sollen, zu diesem Zeitpunkt für die spätere Verwendung in der `OnDragOver` Member-Funktion. Die Ansicht sollte zu diesem Zeitpunkt visuelles Feedback geben auch aktualisiert werden. Weitere Informationen finden Sie im Artikel [per Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="a-nameondragleavea--cviewondragleave"></a><a name="ondragleave"></a>CView::OnDragLeave  
 Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger aus dem Bereich ablegen für dieses Fenster bewegt wird.  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn die aktuelle Ansicht alle ausgeführten Aktionen während der Bereinigung muss [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) aufrufen, z. B. das visuelle Benutzerfeedback entfernen, während das Objekt gezogen und dort abgelegt wurde.  
  
##  <a name="a-nameondragovera--cviewondragover"></a><a name="ondragover"></a>CView::OnDragOver  
 Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger über das Zielfenster bewegt wird.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) über das Ablageziel gezogen wird.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT` Enumerationstyps, der den Typ der Dropdownliste, die auftreten können anzeigt, wenn der Benutzer das Objekt an dieser Position gelöscht. Der Typ des Drop hängt oft von den aktuellen Status durch `dwKeyState`. Eine standardmäßige Zuordnung von Keystates zu `DROPEFFECT` Werte sind:  
  
- `DROPEFFECT_NONE`Das Objekt kann nicht in diesem Fenster gelöscht werden.  
  
- `DROPEFFECT_LINK`für **MK_CONTROL | MK_SHIFT** erstellt eine Verknüpfung zwischen dem Objekt und dem Server.  
  
- `DROPEFFECT_COPY`für **MK_CONTROL** erstellt eine Kopie des gelöschten Objekts.  
  
- `DROPEFFECT_MOVE`für **MK_ALT** erstellt eine Kopie des gelöschten Objekts und löschen Sie das ursprüngliche Objekt. Dies ist normalerweise die Standard-Drop-Effekt, die Ansicht das Datenobjekt annehmen kann.  
  
 Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zu nichts ist `DROPEFFECT_NONE`.  
  
 Überschreiben Sie diese Funktion, um während des Ziehvorgangs visuelles Feedback zu geben. Da diese Funktion kontinuierlich aufgerufen wird, sollten alle darin enthaltenen Code so weit wie möglich optimiert werden. Weitere Informationen finden Sie im Artikel [per Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="a-nameondragscrolla--cviewondragscroll"></a><a name="ondragscroll"></a>CView::OnDragScroll  
 Vor dem Aufruf aufgerufen [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) zu bestimmen, ob der Punkt im Bildlaufbereich ist.  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT` Enumerationstyps, der den Typ der Dropdownliste, die auftreten können anzeigt, wenn der Benutzer das Objekt an dieser Position gelöscht. Die Dropdownliste in der Regel richtet sich nach der aktuellen Tastenzustand erkennbar `dwKeyState`. Eine standardmäßige Zuordnung von Keystates zu `DROPEFFECT` Werte sind:  
  
- `DROPEFFECT_NONE`Das Objekt kann nicht in diesem Fenster gelöscht werden.  
  
- `DROPEFFECT_LINK`für **MK_CONTROL | MK_SHIFT** erstellt eine Verknüpfung zwischen dem Objekt und dem Server.  
  
- `DROPEFFECT_COPY`für **MK_CONTROL** erstellt eine Kopie des gelöschten Objekts.  
  
- `DROPEFFECT_MOVE`für **MK_ALT** erstellt eine Kopie des gelöschten Objekts und löschen Sie das ursprüngliche Objekt.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird, oder in der Ziel-Ansicht erfolgt.  
  
 Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie für dieses Ereignis ein besonderes Verhalten bereitstellen möchten. Die standardmäßige Implementierung wird automatisch Windows, wenn der Cursor in den Bereich innerhalb des Rahmens der einzelnen Fenster einen Bildlauf gezogen wird. Weitere Informationen finden Sie im Artikel [per Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="a-nameondrawa--cviewondraw"></a><a name="ondraw"></a>CView:: OnDraw  
 Aufgerufen, um ein Bild des Dokuments zu rendern.  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern eines Bilds des Dokuments verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um die Bildschirmanzeige, Drucken und Druckvorschau ausführen und in jedem Fall einen anderes Gerätekontext übergeben. Es ist keine Standardimplementierung vorhanden.  
  
 Sie müssen diese Funktion, um die Ansicht des Dokuments anzeigen überschreiben. Aufrufe Grafik Device Interface (GDI) mithilfe der [CDC](../../mfc/reference/cdc-class.md) Objekt verweist die `pDC` Parameter. Auswählen von GDI-Ressourcen, z. B. Stifte oder Schriftarten in den Gerätekontext vor dem Zeichnen und deaktivieren sie anschließend. Häufig kann der Code zum Zeichnen geräteunabhängige sein. d. h. erfordert es nicht Informationen nach Typ des Geräts auf das Bild angezeigt wird.  
  
 Um die Zeichnung weiter zu optimieren, rufen Sie die [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) -Memberfunktion des Gerätekontexts herausfinden, ob ein angegebenes Rechteck gezeichnet wird. Wenn Sie zwischen normalen Bildschirm anzeigen und Drucken unterscheiden müssen, rufen Sie die [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) -Memberfunktion des Gerätekontexts.  
  
##  <a name="a-nameondropa--cviewondrop"></a><a name="ondrop"></a>CView::OnDrop  
 Vom Framework aufgerufen, wenn der Benutzer ein Objekt über ein gültiges Ablageziel loslässt.  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) , die in dem Ablageziel abgelegt wird.  
  
 `dropEffect`  
 Die Drop-Effekt, den der Benutzer angefordert hat.  
  
- `DROPEFFECT_COPY`Erstellt eine Kopie des Objekts gelöscht wird.  
  
- `DROPEFFECT_MOVE`Verschiebt das Objekt an die aktuelle Position des Mauszeigers.  
  
- `DROPEFFECT_LINK`Erstellt einen Link zwischen einem Datenobjekt und den Server.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Dropdownliste erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung keine Aktion aus und gibt **FALSE**.  
  
 Überschreiben Sie diese Funktion, um die Auswirkung der OLE-Drop in den Clientbereich der Ansicht zu implementieren. Das Datenobjekt untersucht werden kann, über `pDataObject` Zwischenablagedaten Formate und Daten gelöscht am angegebenen Punkt.  
  
> [!NOTE]
>  Das Framework nicht diese Funktion aufrufen, wird eine Überschreibung von [OnDropEx](#ondropex) in dieser Ansichtsklasse.  
  
##  <a name="a-nameondropexa--cviewondropex"></a><a name="ondropex"></a>CView::OnDropEx  
 Vom Framework aufgerufen, wenn der Benutzer ein Objekt über ein gültiges Ablageziel loslässt.  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) , die in dem Ablageziel abgelegt wird.  
  
 `dropDefault`  
 Der Effekt, den für die Standard-Drop-Vorgang basierend auf den aktuellen Status der Benutzer ausgewählt hat. Es kann sein `DROPEFFECT_NONE`. Drop-Effekte werden im Abschnitt Hinweise erläutert.  
  
 `dropList`  
 Eine Liste der Drop-Effekte, die die Quelle unterstützt. Drop Effektwerte können kombiniert werden, mit dem bitweisen OR ( **|**) Vorgang. Drop-Effekte werden im Abschnitt Hinweise erläutert.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Drop-Effekt, die aus der Löschversuch am angegebenen Speicherort resultieren `point`. Dies muss einer der Werte, die durch angegebene *DropEffectList*. Drop-Effekte werden im Abschnitt Hinweise erläutert.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zu nichts einen unechten Wert (-1), um anzugeben, dass das Framework aufrufen muss, ist die [OnDrop](#ondrop) Handler.  
  
 Überschreiben Sie diese Funktion, um die Auswirkung einer rechten Maustaste Drag & Drop zu implementieren. Drag & Drop von rechten Maustaste zeigt in der Regel zur Auswahl, wenn die rechte Maustaste losgelassen wird.  
  
 Überschreiben der `OnDropEx` sollte Abfragen, für die rechte Maustaste. Rufen Sie [GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301) oder den Zustand der rechten Maustaste aus speichern Ihre [OnDragEnter](#ondragenter) Handler.  
  
-   Wenn die rechte Maustaste gedrückt ist, sollte die Außerkraftsetzung ein Popup-Menü anzeigen bietet, dass die Quelle der Drop-Effekte unterstützen.  
  
    -   Überprüfen Sie `dropList` bestimmen die Drop-Effekte, die von der Quelle unterstützt. Aktivieren Sie nur diese Aktionen im Popup-Menü.  
  
    -   Verwendung [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) , legen Sie die Standardaktion basierend auf `dropDefault`.  
  
    -   Abschließend führen Sie die Aktion, die durch die Auswahl des Benutzers im Popupmenü angegeben.  
  
-   Ist die rechte Maustaste nicht nach unten, soll überschreiben diese als standard-Drop-Anforderung verarbeiten. Verwenden Sie die Drop-Effekt im angegebenen `dropDefault`. Alternativ kann das Überschreiben den dummy-Wert (1), um anzugeben, dass zurückgegeben `OnDrop` behandelt dieses Drop-Vorgangs.  
  
 Verwendung `pDataObject` untersuchen die `COleDataObject` Zwischenablagedaten Format und Daten gelöscht am angegebenen Punkt.  
  
 Drop-Effekte beschrieben, die ein Drop-Vorgang zugeordnete Aktion. Die folgende Liste der Drop-Effekte angezeigt:  
  
- `DROPEFFECT_NONE`Eine Drop würde nicht zugelassen werden.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel stattfindet.  
  
 Weitere Informationen zum Festlegen des Standard-Menübefehls finden Sie unter [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] und [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) in diesem Handbuch.  
  
##  <a name="a-nameonendprintinga--cviewonendprinting"></a><a name="onendprinting"></a>CView::OnEndPrinting  
 Wird vom Framework aufgerufen, nachdem ein Dokument gedruckt oder in der Vorschau angezeigt wurde.  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um alle GDI-Ressourcen freigeben in zugewiesen wurden die [OnBeginPrinting](#onbeginprinting) Member-Funktion.  
  
##  <a name="a-nameonendprintpreviewa--cviewonendprintpreview"></a><a name="onendprintpreview"></a>CView::OnEndPrintPreview  
 Wird vom Framework aufgerufen, wenn der Benutzer den Seitenansichtmodus verlässt.  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
 `point`  
 Gibt den Punkt auf der Seite, die zuletzt in der Seitenansicht angezeigt wurde.  
  
 `pView`  
 Verweist auf das View-Objekt, das für die Vorschau verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [OnEndPrinting](#onendprinting) -Memberfunktion und der Wiederherstellung begann das Hauptrahmenfenster in den Zustand vor der Seitenansicht war. Überschreiben Sie diese Funktion, um spezielle Verarbeitungsschritte gleichzeitig ausführen, wenn Vorschaumodus beendet wird. Z. B. Wenn Sie die Position des Benutzers im Dokument beibehalten, beim Wechseln von im Vorschaumodus zu normalen Anzeigemodus möchten, wechseln Sie zum die Position von beschrieben die `point` Parameter und die `m_nCurPage` Mitglied der `CPrintInfo` zu strukturieren, dass die `pInfo` -Parameter zeigt.  
  
 Rufen Sie immer die Basisklassenversion von `OnEndPrintPreview` aus der Überschreibung in der Regel am Ende der Funktion.  
  
##  <a name="a-nameoninitialupdatea--cviewoninitialupdate"></a><a name="oninitialupdate"></a>CView:: OnInitialUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber vor dem Beginn der Ansicht angezeigt wird.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [OnUpdate](#onupdate) Memberfunktion ohne Hinweis Informationen (d. h. unter Verwendung der Standardwerte von 0 für die `lHint` Parameter und **NULL** für die `pHint` Parameter). Überschreiben Sie diese Funktion, um die einmalige Initialisierung ausführen, die Informationen über das Dokument erforderlich ist. Beispielsweise verfügt die Anwendung Dokumente mit fester Größe, können dieser Funktion Sie eine Ansicht Bildlauf Grenzen basierend auf der Dokumentgröße zu initialisieren. Wenn Ihre Anwendung variabler Dokumente unterstützt, [OnUpdate](#onupdate) zum Aktualisieren der Bildlauf schränkt jedes Mal das Dokument ändert.  
  
##  <a name="a-nameonpreparedca--cviewonpreparedc"></a><a name="onpreparedc"></a>CView::OnPrepareDC  
 Aufgerufen, bevor die [OnDraw](#ondraw) Memberfunktion aufgerufen wird, für die Bildschirmanzeige und vor der [OnPrint](#onprint) Member-Funktion wird für jede Seite während drucken oder den Seitenansichtmodus aufgerufen.  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern eines Bilds des Dokuments verwendet werden soll.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Auftrag wird beschrieben, wenn `OnPrepareDC` Drucks oder Vorschau; aufgerufen wird der `m_nCurPage` -Member gibt an, die Seite gedruckt werden soll. Dieser Parameter ist **NULL** Wenn `OnPrepareDC` für die Bildschirmanzeige aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion bewirkt nichts, wenn die Funktion für die Bildschirmanzeige aufgerufen wird. Jedoch diese Funktion ist in abgeleiteten Klassen überschrieben, wie z. B. [CScrollView](../../mfc/reference/cscrollview-class.md), Anpassen der Attribute des Gerätekontexts; daher sollten Sie immer Implementierung der Basisklasse aufrufen, am Anfang der Überschreibung.  
  
 Wenn die Funktion zum Drucken aufgerufen wird, überprüft die Implementierung der in gespeicherte Seiteninformationen sind die `pInfo` Parameter. Wenn die Länge des Dokuments nicht angegeben wurde, `OnPrepareDC` geht davon aus dem Dokument eine Seite lang sein und die Druckschleife beendet, nachdem eine Seite gedruckt wurde. Die Funktion beendet die Druckschleife durch Festlegen der `m_bContinuePrinting` Member der Struktur auf **FALSE**.  
  
 Überschreiben Sie `OnPrepareDC` aus einem der folgenden Gründe:  
  
-   Anpassen der Attribute des Gerätekontexts für die angegebene Seite nach Bedarf. Wenn der Zuordnungsmodus oder andere Merkmale des Gerätekontexts festgelegt werden sollen, holen Sie dies z. B. in dieser Funktion.  
  
-   Zum Drucken durchführen. Normalerweise geben Sie die Länge des Dokuments zu Beginn Drucken mithilfe der [OnPreparePrinting](#onprepareprinting) Member-Funktion. Wenn Sie nicht wissen, ist im voraus, wie lange das Dokument (z. B. wenn eine unbestimmte Anzahl von Datensätzen aus einer Datenbank zu drucken) jedoch außer Kraft setzen `OnPrepareDC` für das Ende des Dokuments testen, während es gedruckt wird. Liegt keine weiteren des Dokuments gedruckt werden, legen Sie die `m_bContinuePrinting` Mitglied der `CPrintInfo` Struktur auf **FALSE**.  
  
-   Escapesequenzen, die an den Drucker auf Basis von Seite zu senden. Escapezeichen aus senden `OnPrepareDC`, rufen Sie die **Escape** Memberfunktion der `pDC` Parameter.  
  
 Rufen Sie die Basisklassenversion von `OnPrepareDC` am Anfang der Außerkraftsetzung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#183;](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="a-nameonprepareprintinga--cviewonprepareprinting"></a><a name="onprepareprinting"></a>CView::OnPreparePrinting  
 Vom Framework aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau angezeigt wird.  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Druck beginnen soll, einen Wert ungleich null; 0, wenn der Druckauftrag abgebrochen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Sie müssen diese Funktion zum Drucken und Druckvorschau aktivieren überschreiben. Rufen Sie die [DoPreparePrinting](#doprepareprinting) Member-Funktion, und übergeben sie den `pInfo` -Parameter, und wieder ihren Rückgabewert; `DoPreparePrinting` zeigt das Dialogfeld Drucken und erstellt einen Drucker-Gerätekontext. Wenn Sie das Dialogfeld Drucken mit Werten als die Standardwerte initialisieren möchten, weisen Sie Werte für die Mitglieder `pInfo`. Beispielsweise sollten Sie die Länge des Dokuments übergeben, den Wert, der die [Anzahl](../../mfc/reference/cprintinfo-structure.md#setmaxpage) -Memberfunktion des `pInfo` vor dem Aufruf von `DoPreparePrinting`. Dieser Wert wird im Feld an angezeigt: Feld im Bereich Teil im Dialogfeld Drucken.  
  
 `DoPreparePrinting`Das Dialogfeld "Drucken" für einen Auftrag für die Vorschau wird nicht angezeigt werden. Wenn Sie das Dialogfeld "Drucken" für einen Druckauftrag umgehen möchten, überprüfen Sie, ob die **M_bPreview** Mitglied `pInfo` ist **FALSE** und setzen Sie es auf **TRUE** vor der Übergabe an `DoPreparePrinting`; setzen Sie ihn auf **FALSE** danach.  
  
 Initialisierungen, die Zugriff auf erfordern ggf. die `CDC` darstellt (z. B., wenn Sie die Seitengröße vor benötigen, die die Länge des Dokuments), den Drucker-Gerätekontext Objekt außer Kraft setzen der `OnBeginPrinting` Member-Funktion.  
  
 Wenn der Wert festgelegt werden soll die **M_nNumPreviewPages** oder **M_strPageDesc** Mitglieder der `pInfo` -Parameter, holen Sie dies nach dem Aufruf von `DoPreparePrinting`. Die `DoPreparePrinting` Funktion Elementgruppen **M_nNumPreviewPages** auf den Wert in der Anwendungsverzeichnis. INI-Datei und **M_strPageDesc** auf ihren Standardwert zurück.  
  
### <a name="example"></a>Beispiel  
  Überschreiben Sie `OnPreparePrinting` , und rufen Sie `DoPreparePrinting` aus außer Kraft setzen, damit das Framework ein Drucken-Dialogfeld angezeigt wird, und erstellen einen Drucker-Gerätekontext für Sie.  
  
 [!code-cpp[NVC_MFCDocView&#184;](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 Wenn Sie, wie viele Seiten das Dokument enthält wissen, legen Sie die größte Seitenzahl in `OnPreparePrinting` vor dem Aufruf von `DoPreparePrinting`. Das Framework wird die maximale Seitenzahl in das Feld "an" im Dialogfeld "Drucken" angezeigt.  
  
 [!code-cpp[NVC_MFCDocView&#185;](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="a-nameonprinta--cviewonprint"></a><a name="onprint"></a>CView::OnPrint  
 Vom Framework aufgerufen wird, zu drucken oder die Vorschau einer Seite des Dokuments.  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine `CPrintInfo` -Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion für jede Seite gedruckt wird unmittelbar nach dem Aufrufen der [OnPrepareDC](#onpreparedc) Member-Funktion. Die Seite wird angegeben, indem die `m_nCurPage` Mitglied der [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) zu strukturieren, dass `pInfo` verweist auf. Die standardmäßige Implementierung ruft die [OnDraw](#ondraw) Memberfunktion und übergibt den Gerätekontext.  
  
 Überschreiben Sie diese Funktion für einen der folgenden Gründe:  
  
-   Drucken von mehrseitigen Dokumenten ermöglicht. Rendern Sie nur den Teil des Dokuments, die die gerade gedruckte Seite entspricht. Bei Verwendung von `OnDraw` um das Rendering ausführen, können Sie der Ursprung des Ausschnitts anpassen, so dass nur die entsprechenden Teil des Dokuments gedruckt wird.  
  
-   Machen Sie das gedruckte Bild anders aus als die Bildschirmanzeige (d.h. wenn die Anwendung nicht WYSIWYG ist). Anstelle der Übergabe des Druckers Gerätekontext, `OnDraw`, verwenden Sie den Gerätekontext zum Rendern eines Abbilds mithilfe von Attributen, die nicht auf dem Bildschirm angezeigt.  
  
     Wenn Sie für den Druck GDI-Ressourcen, die nicht für die Bildschirmanzeige verwendet benötigen, wählen Sie diese in den Gerätekontext vor dem Zeichnen und sie anschließend. Diese GDI-Ressourcen zugewiesen werden soll, im [OnBeginPrinting](#onbeginprinting) und veröffentlichte in [OnEndPrinting](#onendprinting).  
  
-   Kopf- und Fußzeilen zu implementieren. Sie können weiterhin verwenden `OnDraw` dazu, dass das Rendering Einschränken des Bereichs, der auf Drucken können.  
  
 Beachten Sie, dass die **M_rectDraw** Mitglied der `pInfo` Parameter beschreibt den Druckbereich der Seite in logischen Einheiten.  
  
 Rufen Sie `OnPrepareDC` in der Überschreibung der `OnPrint`; das Framework ruft `OnPrepareDC` automatisch vor dem Aufruf von `OnPrint`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden finden Sie ein Grundgerüst für eine überschriebene `OnPrint` Funktion:  
  
 [!code-cpp[NVC_MFCDocView&#186;](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect).  
  
##  <a name="a-nameonscrolla--cviewonscroll"></a><a name="onscroll"></a>CView::OnScroll  
 Es ist möglich, aufgerufen, um festzustellen, ob Scrollen.  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nScrollCode`  
 Ein Bildlaufleisten-Code, der den Benutzer angibt, der Anforderung Bildlauf. Dieser Parameter besteht aus zwei Teilen: ein niederwertigen Byte ist, die den Typ des horizontalen Bildlauf auftreten bestimmt wird, und ein höherwertige Byte ist, die vertikal scrollen auftreten bestimmt:  
  
- **SB_BOTTOM** führt einen Bildlauf nach unten.  
  
- **SB_LINEDOWN** verschiebt eine Zeile nach unten.  
  
- **SB_LINEUP** ein Bildlauf um eine Zeile durchgeführt.  
  
- **SB_PAGEDOWN** rollt eine Seite nach unten.  
  
- **SB_PAGEUP** ein Bildlauf um eine Seite durchgeführt.  
  
- **SB_THUMBTRACK** zieht Bildlauffeld, der angegebenen Position. Die aktuelle Position im angegeben `nPos`.  
  
- **SB_TOP** führt einen Bildlauf nach oben.  
  
 `nPos`  
 Die aktuelle Position des Bildlauffelds enthält, wenn der Bildlaufleisten-Code ist **SB_THUMBTRACK**; andernfalls wird er nicht verwendet. Je nach der anfänglichen Bildlaufbereich `nPos` kann negativ sein und sollte in umgewandelt werden ein `int` bei Bedarf.  
  
 `bDoScroll`  
 Bestimmt, ob Sie die angegebene Aktion für die fortlaufende tun sollten. Wenn **"TRUE"** und Durchführen eines Bildlaufs; Wenn stattfinden soll **FALSE**, und klicken Sie dann einen Bildlauf nicht durchgeführt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `bDoScroll` ist **TRUE** und die Ansicht wurde tatsächlich gerollt, fahren Sie andernfalls ungleich 0. Wenn `bDoScroll` ist **FALSE**, fahren Sie den Wert, der Sie Wenn zurückgegeben hätte `bDoScroll` wurden **TRUE**, obwohl Sie eigentlich den Bildlauf nicht tun.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in einem Fall vom Framework mit aufgerufen `bDoScroll` festgelegt **TRUE** Wenn die Sicht eine Bildlaufleiste-Nachricht empfängt. In diesem Fall sollten Sie die Ansicht tatsächlich blättern. Im anderen Fall wird mit dieser Funktion aufgerufen `bDoScroll` festgelegt **FALSE** Wenn ein OLE-Element anfänglich gezogen wird in den automatischen Bildlauf-Bereich eines Dropziels vor dem Durchführen eines Bildlaufs tatsächlich ausgeführt wird. In diesem Fall sollten Sie die Ansicht nicht tatsächlich blättern.  
  
##  <a name="a-nameonscrollbya--cviewonscrollby"></a><a name="onscrollby"></a>CView::OnScrollBy  
 Wird vom Framework aufgerufen, wenn der Benutzer einen Bereich außerhalb der vorhanden Ansicht des Dokuments an, entweder durch ein OLE-Element für die Ansicht des aktuellen Rahmen ziehen oder bearbeiten die vertikalen oder horizontalen Bildlaufleisten anzeigt.  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeScroll`  
 Anzahl der Pixel Bildlauf horizontal und vertikal.  
  
 `bDoScroll`  
 Bestimmt, ob der Bildlauf der Ansicht auftritt. Wenn **"TRUE"** und Bildlauf; Wenn erfolgt **FALSE**, dann Bildlauf nicht auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Ansicht ein Bildlauf durchgeführt werden konnte; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In abgeleiteten Klassen überprüft diese Methode, ob die Ansicht bildlauffähigen in Richtung der Benutzer angefordert und aktualisiert dann die neue Region aus, bei Bedarf. Diese Funktion wird automatisch aufgerufen, indem [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) die tatsächliche Bildlauf Anforderung ausführen.  
  
 Die standardmäßige Implementierung dieser Methode wird die Ansicht nicht geändert, aber wenn sie nicht aufgerufen wird, wird keine Bildlauf einem `CScrollView`-abgeleiteten Klasse.  
  
 Wenn die Breite oder Höhe 32767 Pixel überschreitet, Durchführen eines Bildlaufs nach 32767 schlägt fehl, da `OnScrollBy` aufgerufen wird und eine ungültige `sizeScroll` Argument.  
  
##  <a name="a-nameonupdatea--cviewonupdate"></a><a name="onupdate"></a>CView::OnUpdate  
 Wird vom Framework aufgerufen, nachdem die Ansicht Dokument geändert wurde; Diese Funktion wird aufgerufen, indem [UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) und die Ansicht seine Anzeige diese Änderungen entsprechend aktualisiert.  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>Parameter  
 `pSender`  
 Verweist auf die Ansicht, die das Dokument geändert oder **NULL** alle Ansichten sind, aktualisiert werden.  
  
 `lHint`  
 Enthält Informationen zu den Änderungen an.  
  
 `pHint`  
 Verweist auf ein Objekt, das Informationen zu den Änderungen zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Sie wird auch aufgerufen, durch die standardmäßige Implementierung des [OnInitialUpdate](#oninitialupdate). Die standardmäßige Implementierung erklärt den gesamten Clientbereich, markieren es für das Zeichnen, wenn die nächste `WM_PAINT` Nachricht empfangen wird. Überschreiben Sie diese Funktion, wenn Sie nur die Bereiche zu aktualisieren, die die geänderten Teile des Dokuments zuordnen möchten. Zu diesem Zweck müssen Sie Informationen zu den Änderungen, die unter Verwendung der Hinweis-Parameter übergeben.  
  
 Mit `lHint`Hinweis spezielle Werte, in der Regel eine Bitmaske oder ein enumerierter Typ definiert und das Dokument, übergeben Sie einen der folgenden Werte haben. Verwenden `pHint`, leiten Sie eine Klasse Hinweis aus [CObject](../../mfc/reference/cobject-class.md) und das Dokument einen Zeiger auf ein Objekt Hinweis übergeben, beim Überschreiben `OnUpdate`, verwenden die [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) Member-Funktion, um den Laufzeittyp des Objekts Hinweis zu bestimmen.  
  
 In der Regel führen Sie eine Zeichnung direkt aus `OnUpdate`. Stattdessen bestimmen Sie das Rechteck beschreiben, in logische Koordinaten, den Bereich, der aktualisieren erforderlich ist. übergeben Sie dieses Rechteck [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect). Dies bewirkt, dass Zeichnen auf das nächste Mal eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht empfangen wird.  
  
 Wenn `lHint` ist 0 und `pHint` ist **NULL**, das Dokument verfügt über eine generische Benachrichtigung gesendet. Wenn eine Sicht eine generische Benachrichtigung empfängt, oder wenn die Hinweise nicht decodiert werden können, sollte es den gesamten Clientbereich ungültig.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)

