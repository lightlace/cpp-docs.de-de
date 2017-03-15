---
title: CDocument-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocument
dev_langs:
- C++
helpviewer_keywords:
- documents [C++], serialization
- files [C++], documents
- command handling, documents and
- documents [C++], document classes
- documents [C++], multiple views
- serialization [C++], documents and
- CDocument class
- command routing, documents and
- views [C++], document
- documents [C++], command routing
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
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
ms.openlocfilehash: 4d64b95f77139d984b855e710f3951434e489dd5
ms.lasthandoff: 02/24/2017

---
# <a name="cdocument-class"></a>CDocument-Klasse
Stellt die grundlegende Funktionalität für benutzerdefinierte Dokumentklassen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|Erstellt ein `CDocument`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument:: AddView](#addview)|Fügt eine Sicht auf das Dokument.|  
|[CDocument::BeginReadChunks](#beginreadchunks)|Initialisiert Block lesen.|  
|[CDocument::CanCloseFrame](#cancloseframe)|Erweiterte überschrieben; vor dem Schließen eines Rahmenfensters dieses Dokument aufgerufen.|  
|[CDocument::ClearChunkList](#clearchunklist)|Löscht die Liste der Block.|  
|[CDocument::ClearPathName](#clearpathname)|Löscht den Pfad des Document-Objekts.|  
|[CDocument::DeleteContents](#deletecontents)|Wird aufgerufen, um die Bereinigung des Dokuments durchzuführen.|  
|[CDocument::FindChunk](#findchunk)|Sucht ein Segment mit der angegebenen GUID.|  
|[CDocument::GetAdapter](#getadapter)|Gibt einen Zeiger auf das Objekt implementiert `IDocument` Schnittstelle.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|Gibt einen Zeiger auf die Dokumentvorlage, die den Typ des Dokuments beschreibt.|  
|[CDocument::GetFile](#getfile)|Gibt einen Zeiger auf die gewünschte `CFile` Objekt.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Gibt die Position des ersten in der Liste der Ansichten; verwendet, um die Iteration starten.|  
|[CDocument::GetNextView](#getnextview)|Durchläuft die Liste der Ansichten, die dem Dokument zugeordnet.|  
|[CDocument::GetPathName](#getpathname)|Gibt den Pfad der Datendatei für das Dokument.|  
|[CDocument::GetThumbnail](#getthumbnail)|Wird aufgerufen, um eine Bitmap von Miniaturansicht-Provider verwendet werden, um die Miniaturansicht anzuzeigen zu erstellen.|  
|[CDocument::GetTitle](#gettitle)|Gibt den Titel des Dokuments zurück.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Zum Initialisieren der Inhalte durchsuchen für Suche-Handler aufgerufen.|  
|[CDocument::IsModified](#ismodified)|Gibt an, ob das Dokument geändert wurde, seit es zuletzt gespeichert wurde.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Informiert, ob diese Instanz von `CDocument` Objekt für Suche & organisieren-Ereignishandler erstellt wurde.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Zum Laden von Daten aus Stream aufgerufen.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Aufgerufen, bevor Rich Preview Schriftart geändert wird.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|Wird aufgerufen, nachdem eine Sicht hinzugefügt oder aus dem Dokument entfernt.|  
|[CDocument::OnCloseDocument](#onclosedocument)|Wird aufgerufen, um das Dokument zu schließen.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Wird vom Framework aufgerufen, wenn einen Frame Preview for Rich Preview erstellt werden müssen.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|Wird vom Framework als Reaktion auf ein Dokumentereignis aufgerufen.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Inhalt der Miniaturansicht zu zeichnen.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Wird vom Framework aufgerufen, wenn die Daten aus Stream geladen werden müssen.|  
|[CDocument::OnNewDocument](#onnewdocument)|Wird aufgerufen, um ein neues Dokument erstellen.|  
|[Funktionen](#onopendocument)|Wird aufgerufen, um ein vorhandenes Dokument zu öffnen.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Weist den Vorschauhandler das HWND zurückgeben, die GetFocus-Funktion aufrufen.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Weist den Vorschauhandler verarbeitet eine Tastatureingabe nach oben weitergegeben wird, aus dem Nachrichtensystem des Prozesses, in dem der Vorschauhandler ausgeführt wird.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Wird aufgerufen, wenn umfangreiche Vorschau der Hintergrundfarbe geändert hat.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Wird aufgerufen, wenn Rich Preview Schriftart geändert hat.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Wird aufgerufen, wenn umfangreiche Vorschau-Website geändert hat.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Wird aufgerufen, wenn Rich Textfarbe geändert hat.|  
|[CDocument::OnSaveDocument](#onsavedocument)|Wird aufgerufen, um das Dokument auf der Festplatte zu speichern.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|Wird vom Framework aufgerufen, wenn der Vorschauhandler entladen wird.|  
|[CDocument::PreCloseFrame](#precloseframe)|Aufgerufen, bevor die Frame-Fenster geschlossen wird.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Liest die nächsten Segment-Wert.|  
|[CDocument::ReleaseFile](#releasefile)|Gibt eine Datei von einer anderen Anwendung verfügbar zu machen.|  
|[CDocument::RemoveChunk](#removechunk)|Entfernt ein Segment mit der angegebenen GUID.|  
|[CDocument::RemoveView](#removeview)|Trennt eine Ansicht aus dem Dokument.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Erweiterte überschrieben; wird aufgerufen, wenn eine offene oder Speichervorgang nicht aufgrund einer Ausnahme abgeschlossen werden.|  
|[SaveModified](#savemodified)|Erweiterte überschrieben; wird aufgerufen, um den Benutzer zu Fragen, ob das Dokument gespeichert werden soll.|  
|[CDocument::SetChunkValue](#setchunkvalue)|Legt einen Block-Wert.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Legt ein Flag, das angibt, dass Sie das Dokument geändert haben, seit es zuletzt gespeichert wurde.|  
|[CDocument::SetPathName](#setpathname)|Gibt den Pfad der Datendatei vom Dokument verwendet.|  
|[CDocument::SetTitle](#settitle)|Legt den Titel des Dokuments.|  
|[UpdateAllViews](#updateallviews)|Benachrichtigt alle Ansichten, das Dokument geändert wurde.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument:: OnFileSendMail](#onfilesendmail)|Sendet eine e-Mail-Nachricht mit dem Dokument angefügt.|  
|[CDocument:: OnUpdateFileSendMail](#onupdatefilesendmail)|Können den Befehl E-Mail senden, wenn e-Mail-Unterstützung vorhanden ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Gibt an, dass `CDocument` Objekt von Dllhost für Miniaturansichten erstellt wurde. Überprüft werden soll, im `CView::OnDraw`.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Gibt an, dass `CDocument` wurde erstellt, indem Prevhost für `Rich Preview`. Überprüft werden soll, im `CView::OnDraw`.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|Gibt an, dass `CDocument` Objekt wurde von Indexer oder einer anderen Suchanwendung.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Gibt die Hintergrundfarbe des Rich-Vorschaufenster. Diese Farbe wird vom Host festgelegt.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Gibt die Vordergrundfarbe des Rich-Vorschaufenster. Diese Farbe wird vom Host festgelegt.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Gibt die Schriftart für Rich-Vorschaufenster. Diese Schriftartinformationen wird vom Host festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Dokument repräsentiert die Dateneinheit, die der Benutzer normalerweise mit dem Befehl Datei geöffnet und mit dem Befehl Speichern speichert.  
  
 **CDocument** unterstützt Standardvorgänge wie z. B. ein Dokument zu erstellen, laden und speichern. Das Framework bearbeitet, Dokumente, die über die Benutzeroberfläche definiert **CDocument**.  
  
 Eine Anwendung kann mehr als einen Typ des Dokuments unterstützen; eine Anwendung kann z. B. Kalkulationstabellen und Text-Dokumenten unterstützen. Jeder Dokument verfügt über eine zugeordnete Dokumentvorlage; die Dokumentvorlage gibt an, welche Ressourcen (z. B. Menüs, Symbol oder Accelerator-Tabelle) für diesen Dokumenttyp verwendet werden. Jedes Dokument enthält einen Zeiger auf die zugehörigen `CDocTemplate` Objekt.  
  
 Benutzer interagieren mit einem Dokument über die [CView](../../mfc/reference/cview-class.md) Objekten zugeordnet. Eine Ansicht stellt ein Bild des Dokuments in einem Rahmenfenster und Benutzereingaben als Vorgänge des Dokuments interpretiert. Ein Dokument kann mehrere Sichten zugeordnet haben. Wenn der Benutzer ein Fenster auf ein Dokument öffnet, wird das Framework eine Sicht erstellt und an das Dokument angefügt. Die Dokumentvorlage gibt an, welche Art von Ansicht und dem Rahmenfenster werden verwendet, um jeden Typ von Dokument anzuzeigen.  
  
 Dokumente sind Teil des Frameworks Standard Befehl routing und daher empfangen Befehle von standardmäßigen Benutzeroberflächen-Komponenten (z. B. das Menüelement speichern). Ein Dokument erhält die Befehle, die von der aktiven Ansicht weitergeleitet. Wenn das Dokument einen bestimmten Befehl nicht behandelt, wird den Befehl die Dokumentvorlage, die sie verwalten weitergeleitet.  
  
 Wenn Daten eines Dokuments geändert werden, muss jede Ansichten diese Änderungen wider. **CDocument** bietet die [UpdateAllViews](#updateallviews) Member-Funktion für Sie die Ansichten der Art, benachrichtigen, damit die Ansichten selbst nach Bedarf aktualisieren können. Das Framework auch der Benutzer aufgefordert, eine geänderte Datei vor dem Schließen gespeichert.  
  
 Um Dokumente in einer normalen Anwendung zu implementieren, müssen Sie Folgendes ausführen:  
  
-   Leiten Sie eine Klasse von **CDocument** für jeden Typ des Dokuments.  
  
-   Hinzufügen von Membervariablen zum Speichern der Daten des Dokuments.  
  
-   Implementieren Sie die Memberfunktionen für das Lesen und ändern die Daten des Dokuments. Die Ansichten des Dokuments sind die wichtigsten Benutzer diese Memberfunktionen.  
  
-   Überschreiben der [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) Member-Funktion in der Dokumentklasse, die Daten des Dokuments zum und vom Datenträger gelesen und geschrieben.  
  
 **CDocument** unterstützt das Dokument über e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Weitere Informationen zu **CDocument**, finden Sie unter [Serialisierung](../../mfc/serialization-in-mfc.md), [von Dokument/Ansicht-Architektur Themen](../../mfc/document-view-architecture.md), und [von Dokument/Ansicht-Erstellung](../../mfc/document-view-creation.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-nameaddviewa--cdocumentaddview"></a><a name="addview"></a>CDocument:: AddView  
 Rufen Sie diese Funktion, um eine Sicht an das Dokument anfügen.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pView`  
 Verweist auf die Sicht hinzugefügt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion fügt die angegebene Ansicht zur Liste der Ansichten, die dem Dokument zugeordnet; die Funktion setzt auch die Ansicht Dokument Zeiger zu diesem Dokument. Das Framework ruft diese Funktion auf, wenn ein Dokument ein neu erstelltes Objekt zuordnen; Dieser Fehler tritt in Reaktion auf eine neue Datei, Datei öffnen oder neuen Fenster Befehl oder wenn ein unterteiltes Fenster geteilt wird.  
  
 Rufen Sie diese Funktion nur, wenn Sie manuell erstellen und Anfügen eine Ansicht. In der Regel können Sie das Framework Verbinden von Dokumenten und Ansichten definieren einer [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt zuordnen einer Dokumentklasse Ansichtsklasse und Rahmenfenster (Klasse).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI&#12;](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="a-namebeginreadchunksa--cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 Initialisiert Block lesen.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecancloseframea--cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument::CanCloseFrame  
 Vom Framework aufgerufen, bevor ein Frame-Fenster das Dokument geschlossen wird.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrame`  
 Verweist auf das Rahmenfenster einer Ansicht, die dem Dokument zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es sicher ist, schließen Sie das Rahmenfenster ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung überprüft, ob andere Rahmenfenster, Dokument anzeigen. Ist das angegebene Rahmenfenster zuletzt, in dem das Dokument angezeigt, die Funktion der Benutzer aufgefordert, das Dokument zu speichern, wenn es geändert wurde. Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung beim Schließen eines Rahmenfensters ausführen möchten. Dies ist eine erweiterte überschrieben.  
  
##  <a name="a-namecdocumenta--cdocumentcdocument"></a><a name="cdocument"></a>CDocument::CDocument  
 Erstellt eine **CDocument** Objekt.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ist die Erstellung für Sie. Überschreiben Sie die [OnNewDocument](#onnewdocument) Memberfunktion zum Ausführen der Initialisierung auf Basis pro Dokument; Dies ist besonders wichtig in einzelnen Document Interface (SDI) Anwendung.  
  
##  <a name="a-nameclearchunklista--cdocumentclearchunklist"></a><a name="clearchunklist"></a>CDocument::ClearChunkList  
 Löscht die Liste der Block.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameclearpathnamea--cdocumentclearpathname"></a><a name="clearpathname"></a>CDocument::ClearPathName  
 Löscht den Pfad des Document-Objekts.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>Hinweise  
 Löschen den Pfad aus einem `CDocument` Objekt bewirkt, dass die Anwendung den Benutzer auffordern, wenn das Dokument anschließend gespeichert wird. Dadurch wird eine **speichern** Befehl verhält sich wie eine **speichern** Befehl.  
  
##  <a name="a-namedeletecontentsa--cdocumentdeletecontents"></a><a name="deletecontents"></a>CDocument::DeleteContents  
 Aufgerufen, so löschen Sie die Daten des Dokuments ohne Löschen der **CDocument** Objekt selbst.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie wird aufgerufen, unmittelbar bevor das Dokument wird zerstört werden. Sie wird auch aufgerufen, um sicherzustellen, dass ein Dokument leer ist, bevor er wiederverwendet wird. Dies ist besonders wichtig für eine SDI-Anwendung, die nur ein Dokument verwendet. das Dokument wird wiederverwendet, wenn der Benutzer erstellt oder ein anderes Dokument öffnet. Rufen Sie diese Funktion zum Implementieren einer "Bearbeiten Alle löschen" oder ähnlichen Befehl, der alle Daten des Dokuments gelöscht. Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um die Daten im Dokument zu löschen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#57;](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="a-namefindchunka--cdocumentfindchunk"></a><a name="findchunk"></a>CDocument::FindChunk  
 Sucht nach einem Segment mit einer angegebenen GUID.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Parameter  
 `guid`  
 Gibt die GUID eines gefunden.  
  
 `pid`  
 Gibt eine PID eines gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position in der internen Segment bei Erfolg. Andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetadaptera--cdocumentgetadapter"></a><a name="getadapter"></a>CDocument::GetAdapter  
 Gibt einen Zeiger auf ein Objekt, das die `IDocument` Schnittstelle.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Objekt, das die `IDocument` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetdoctemplatea--cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 Rufen Sie diese Funktion, um einen Zeiger auf die Dokumentvorlage für diesen Dokumenttyp.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Dokumentvorlage für diesen Dokumenttyp oder **NULL** , wenn das Dokument nicht von einer Dokumentvorlage verwaltet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#58;](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="a-namegetfilea--cdocumentgetfile"></a><a name="getfile"></a>CDocument::GetFile  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf ein `CFile` Objekt.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zur gewünschten Datei. Der Pfad kann relativ oder absolut sein.  
  
 `pError`  
 Ein Zeiger auf eine vorhandene Datei-Ausnahme-Objekt, das den Abschlussstatus des Vorgangs angibt.  
  
 `nOpenFlags`  
 Gemeinsame Nutzung und Zugriffsmodus. Gibt die Aktion an, die beim Öffnen der Datei. Im Konstruktor CFile aufgeführten Optionen können kombiniert werden [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) mit dem bitweisen OR-Operator (|). Eine Access-Berechtigung und eine Freigabe-Option ist erforderlich. die **ModeCreate** und **ModeNoInherit** Modi sind optional.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CFile` Objekt.  
  
##  <a name="a-namegetfirstviewpositiona--cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 Rufen Sie diese Funktion, um die Position der ersten Ansicht in der Liste der Ansichten, die mit dem Dokument verknüpfte abzurufen.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration mit verwendet werden, kann der [GetNextView](#getnextview) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetnextviewa--cdocumentgetnextview"></a><a name="getnextview"></a>CDocument::GetNextView  
 Mit dieser Funktion werden alle Ansichten des Dokuments durchlaufen.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen Aufruf zurückgegebene Wert der `GetNextView` oder [Sie GetFirstViewPosition](#getfirstviewposition) Memberfunktionen. Dieser Wert darf nicht sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Ansicht identifizierten `rPosition`.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt die Ansicht durch identifiziert `rPosition` und legt dann `rPosition` an der **POSITION** Wert, der die nächste Ansicht in der Liste. Wenn die abgerufene Ansicht das letzte Element in der Liste dann ist `rPosition` Wert **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetpathnamea--cdocumentgetpathname"></a><a name="getpathname"></a>CDocument::GetPathName  
 Rufen Sie diese Funktion, um den vollqualifizierten Pfad der Datei des Dokuments zu erhalten.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Dokument vollständig qualifizierten Pfad. Diese Zeichenfolge ist leer, wenn das Dokument nicht gespeichert noch oder verfügt nicht über eine Datenträgerdatei zugeordnet.  
  
##  <a name="a-namegetthumbnaila--cdocumentgetthumbnail"></a><a name="getthumbnail"></a>CDocument::GetThumbnail  
 Erstellt eine Bitmap, die von den Miniaturansicht-Provider verwendet werden, um die Miniaturansicht anzuzeigen.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Gibt die Breite und Höhe der Bitmap.  
  
 `phbmp`  
 Ein Handle für eine Bitmap enthält, wenn die Funktion erfolgreich ausgeführt wurde.  
  
 `pdwAlpha`  
 Enthält einen DWORD-Wert, der Wert des Alphakanals angeben, wenn die Funktion erfolgreich ausgeführt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` eine Bitmap für die Miniaturansicht erstellt wurde, wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettitlea--cdocumentgettitle"></a><a name="gettitle"></a>CDocument::GetTitle  
 Rufen Sie diese Funktion, um den Titel des Dokuments, zu erhalten, die in der Regel aus dem Dateinamen des Dokuments abgeleitet ist.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel des Dokuments.  
  
##  <a name="a-nameinitializesearchcontenta--cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 Zum Initialisieren der Inhalte durchsuchen für den Search-Handler aufgerufen.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um Inhalte durchsuchen zu initialisieren. Der Inhalt muss eine Zeichenfolge mit Teilen, getrennt durch ";". Z. B. "verweisen. Rechteck; OLE-Element".  
  
##  <a name="a-nameismodifieda--cdocumentismodified"></a><a name="ismodified"></a>CDocument::IsModified  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Dokument geändert wurde, seit es zuletzt gespeichert wurde.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument geändert wurde, seit es zuletzt gespeichert wurde; andernfalls 0.  
  
##  <a name="a-nameissearchandorganizehandlera--cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 Informiert, ob diese Instanz von `CDocument` für die Suche & organisieren-Ereignishandler erstellt wurde.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn diese Instanz von `CDocument` für die Suche & organisieren-Ereignishandler erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zurzeit zurück `TRUE` nur für Rich-Vorschauhandler in einer Out-of Process-Server implementiert. Sie können den geeigneten Flags (M_bPreviewHandlerMode, M_bSearchMode M_bGetThumbnailMode) festlegen, auf der Anwendungsebene vornehmen dieser Funktion `TRUE`.  
  
##  <a name="a-nameloaddocumentfromstreama--cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 Wird aufgerufen, um das Laden von Daten aus einem Stream.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 Ein Zeiger auf einen Stream. Dieser Datenstrom wird von der Shell bereitgestellt.  
  
 `dwGrfMode`  
 Der Zugriffsmodus in den Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Ladevorgang erfolgreich war, andernfalls HRESULT mit einem Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode in einer abgeleiteten Klasse zum Laden von Daten aus dem Stream anpassen überschreiben.  
  
##  <a name="a-namembgetthumbnailmodea--cdocumentmbgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 Gibt an, dass die `CDocument` Objekt von Dllhost für Miniaturansichten erstellt wurde. Überprüft werden soll, im `CView::OnDraw`.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass das Dokument Dllhost für Miniaturansichten erstellt wurde.  
  
##  <a name="a-namembpreviewhandlermodea--cdocumentmbpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 Gibt an, dass die `CDocument` Objekt wurde von Prevhost for Rich Preview. Überprüft werden soll, im `CView::OnDraw`.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass das Dokument Prevhost for Rich Preview erstellt wurde.  
  
##  <a name="a-namembsearchmodea--cdocumentmbsearchmode"></a><a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 Gibt an, dass die `CDocument` Objekt Indexer oder einer anderen Search-Anwendung erstellt wurde.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass das Dokument, oder von einer anderen Anwendung von Search Indexer erstellt wurde.  
  
##  <a name="a-namemclrrichpreviewbackcolora--cdocumentmclrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 Gibt die Hintergrundfarbe des Fensters Rich Preview. Diese Farbe wird vom Host festgelegt.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemclrrichpreviewtextcolora--cdocumentmclrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 Gibt die Vordergrundfarbe des Rich-Vorschaufenster. Diese Farbe wird vom Host festgelegt.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemlfrichpreviewfonta--cdocumentmlfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 Gibt die Schriftart für das Vorschaufenster Rich Text. Diese Schriftartinformationen wird vom Host festgelegt.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonbeforerichpreviewfontchangeda--cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 Aufgerufen, bevor die umfassende Vorschau Schriftart geändert wird.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonchangedviewlista--cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 Wird vom Framework aufgerufen, nachdem eine Sicht hinzugefügt oder aus dem Dokument entfernt.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion wird überprüft, ob die letzte Ansicht entfernt wird, und wenn dies der Fall ist, das Dokument löscht. Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung durch, wenn das Framework hinzufügt oder eine Sicht entfernt ausführen möchten. Z. B. wenn ein Dokument geöffnet bleiben, auch wenn es keine Sichten angefügt sind werden soll, überschreiben Sie diese Funktion.  
  
##  <a name="a-nameonclosedocumenta--cdocumentonclosedocument"></a><a name="onclosedocument"></a>CDocument::OnCloseDocument  
 Wird vom Framework aufgerufen, wenn das Dokument, in der Regel als Teil des Befehls Datei schließen geschlossen wird.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion löscht alle Frames zum Anzeigen des Dokuments, schließt die Ansicht, den Inhalt des Dokuments bereinigt und ruft dann die [DeleteContents](#deletecontents) Memberfunktion, um die Daten des Dokuments löschen.  
  
 Überschreiben Sie diese Funktion, wenn Sie spezielle Bereinigung verarbeiten, wenn das Framework ein Dokument schließt ausführen möchten. Z. B. wenn das Dokument einen Datensatz in einer Datenbank darstellt, können Sie diese Funktion, um die Datenbank zu schließen überschreiben möchten. Sie sollten die Basisklassenversion dieser Funktion in der Überschreibung aufrufen.  
  
##  <a name="a-nameoncreatepreviewframea--cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 Wird vom Framework aufgerufen, wenn einen Frame Preview for Rich Preview erstellt werden müssen.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` wird der Frame wurde; andernfalls erstellt `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondocumenteventa--cdocumentondocumentevent"></a><a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 Wird vom Framework als Reaktion auf ein Dokumentereignis aufgerufen.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `deEvent`  
 Enumerierten Datentyps, der den Typ des Ereignisses beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Dokumentereignisse können mehrere Klassen auswirken. Diese Methode ist verantwortlich für die Behandlung von Ereignissen, die als Klassen Einfluss auf die [CDocument-Klasse](../../mfc/reference/cdocument-class.md). Derzeit ist die einzige Klasse, die auf Ereignissen reagieren muss, ist die [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md). Die `CDocument` -Klasse verfügt über andere überschreibbare Methoden, die verantwortlich für die Behandlung der Auswirkung auf die `CDocument`.  
  
 Die folgende Tabelle enthält die möglichen Werte für `deEvent` und die Ereignisse, die sie entsprechen.  
  
|Wert|Entsprechende Ereignis|  
|-----------|-------------------------|  
|`onAfterNewDocument`|Ein neues Dokument erstellt wurde.|  
|`onAfterOpenDocument`|Es wurde ein neues Dokument geöffnet.|  
|`onAfterSaveDocument`|Das Dokument wurde gespeichert.|  
|`onAfterCloseDocument`|Das Dokument wurde geschlossen.|  
  
##  <a name="a-nameondrawthumbnaila--cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um die Miniaturansicht zu zeichnen.  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Ein Verweis zu einem Gerätekontext.  
  
 `lprcBounds`  
 Gibt ein umschließendes Rechteck für den Bereich, in dem die Miniaturansicht gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonfilesendmaila--cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>CDocument:: OnFileSendMail  
 Sendet eine Nachricht über den residenten Mailhost (sofern vorhanden) mit dem Dokument als Anlage.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnFileSendMail`Aufrufe [OnSaveDocument](#onsavedocument) (Speichern) neue und geänderte Dokumente in eine temporäre Datei serialisiert werden soll, die dann per e-Mail gesendet wird. Wenn das Dokument nicht geändert wurde, wird eine temporäre Datei nicht erforderlich. die ursprüngliche wird gesendet. `OnFileSendMail`Lädt MAPI32. DLL, wenn er nicht bereits geladen wurde.  
  
 Eine spezielle Implementierung der `OnFileSendMail` für [COleDocument](../../mfc/reference/coledocument-class.md) Verbunddateien ordnungsgemäß behandelt.  
  
 **CDocument** unterstützt das Dokument über e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="a-nameonloaddocumentfromstreama--cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 Wird vom Framework aufgerufen, wenn die Daten aus einem Stream geladen werden müssen.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 Ein Zeiger auf einen eingehenden Datenstrom.  
  
 `grfMode`  
 Der Zugriffsmodus in den Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Ladevorgang erfolgreich ist; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonnewdocumenta--cdocumentonnewdocument"></a><a name="onnewdocument"></a>CDocument::OnNewDocument  
 Vom Framework als Teil des Befehls neue Datei aufgerufen.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [DeleteContents](#deletecontents) Member-Funktion, um sicherzustellen, dass das Dokument leer ist, und klicken Sie dann das neue Dokument als sauber markiert. Überschreiben Sie diese Funktion, um die Datenstruktur für ein neues Dokument zu initialisieren. Sie sollten die Basisklassenversion dieser Funktion in der Überschreibung aufrufen.  
  
 Wenn der Benutzer den Befehl neue Datei in einer SDI-Anwendung, verwendet das Framework diese Funktion zum erneuten initialisieren das bestehende Dokument, anstatt einen neuen zu erstellen. Wenn der Benutzer neue Datei in eine Anwendung für multiple Document Interface (MDI), wird das Framework erstellt ein neues Dokument, das jedes Mal, und ruft dann diese Funktion, um sie zu initialisieren. Sie müssen den Initialisierungscode in dieser Funktion anstatt im Konstruktor für die neue Datei Befehl effektiv in SDI-Anwendung platzieren.  
  
 Beachten Sie, dass es Fälle, in denen `OnNewDocument` wird zweimal aufgerufen. Dies tritt auf, wenn das Dokument als ActiveX-Dokument eingebettet ist. Die Funktion wird zuerst aufgerufen, indem die `CreateInstance` Methode (verfügbar gemacht werden, indem Sie die `COleObjectFactory`-abgeleiteten Klasse) und ein zweites Mal von der `InitNew` Methode (verfügbar gemacht werden, indem die `COleServerDoc`-abgeleitete Klasse).  
  
### <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen die alternative Methoden zum Initialisieren von ein Document-Objekt.  
  
 [!code-cpp[NVC_MFCDocView&60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="a-nameonopendocumenta--cdocumentonopendocument"></a><a name="onopendocument"></a>Funktionen  
 Vom Framework aufgerufen wird als Teil des Befehls Datei öffnen.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf den Pfad des Dokuments, das geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion öffnet die angegebene Datei ist, ruft der [DeleteContents](#deletecontents) Member-Funktion, um sicherzustellen, dass das Dokument leer ist, ruft [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) zum Lesen der Datei's Inhalt, und klicken Sie dann das Dokument als sauber markiert. Überschreiben Sie diese Funktion, wenn Sie etwas als der Mechanismus Archiv oder der dateimechanismus verwenden möchten. Z. B. können Sie eine Anwendung schreiben, wobei Dokumente Datensätze in eine Datenbank statt in separaten Dateien darstellen.  
  
 Wenn der Benutzer den Befehl Datei in einer SDI-Anwendung auswählt, verwendet das Framework diese Funktion erneut initialisieren die vorhandene **CDocument** -Objekt, statt einen neuen zu erstellen. Wenn der Benutzer in einer MDI-Anwendung geöffneten Datei auswählt, erstellt das Framework ein neues **CDocument** Objekt jedes Mal ein und ruft dann diese Funktion, um sie zu initialisieren. Sie müssen den Initialisierungscode in dieser Funktion anstatt im Konstruktor für den Befehl Datei effektiv in SDI-Anwendung platzieren.  
  
### <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen die alternative Methoden zum Initialisieren von ein Document-Objekt.  
  
 [!code-cpp[NVC_MFCDocView&60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#63;](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="a-nameonpreviewhandlerqueryfocusa--cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 Weist den Vorschauhandler das HWND abgerufen durch den Aufruf der `GetFocus` Funktion.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>Parameter  
 `phwnd`  
 [out] Bei Rückgabe dieser Methode enthält einen Zeiger auf das HWND zurückgegeben, die durch den Aufruf der `GetFocus` -Funktion aus dem Vorschauhandler Vordergrundthread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn erfolgreich. oder einen Fehler zurück, die andernfalls.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpreviewhandlertranslateacceleratora--cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 Weist den Vorschauhandler verarbeitet eine Tastatureingabe nach oben weitergegeben wird, aus dem Nachrichtensystem des Prozesses, in dem der Vorschauhandler ausgeführt wird.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pmsg`  
 [in] Ein Zeiger auf eine Meldung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Tastaturanschlag-Nachricht von der Vorschauhandler verarbeitet werden kann, wird der Handler verarbeitet sie und gibt S_OK zurück. Wenn der Vorschauhandler die Tastatureingabe verarbeiten kann, bietet es an dem Host über `IPreviewHandlerFrame::TranslateAccelerator`. Wenn der Host die Nachricht verarbeitet wird, gibt diese Methode S_OK zurück. Wenn der Host die Nachricht nicht verarbeitet, wird von dieser Methode S_FALSE zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonrichpreviewbackcolorchangeda--cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 Wird aufgerufen, wenn die Hintergrundfarbe Rich Preview geändert hat.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonrichpreviewfontchangeda--cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 Wird aufgerufen, wenn die Schriftart Rich Preview geändert hat.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonrichpreviewsitechangeda--cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 Wird aufgerufen, wenn die umfangreiche Vorschau-Website geändert hat.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonrichpreviewtextcolorchangeda--cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 Wird aufgerufen, wenn die Textfarbe Rich Preview geändert hat.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsavedocumenta--cdocumentonsavedocument"></a><a name="onsavedocument"></a>CDocument::OnSaveDocument  
 Vom Framework als Teil des Befehls Speichern oder Datei speichern unter aufgerufen.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf den vollqualifizierten Pfad, in dem die Datei gespeichert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich gespeichert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion die angegebene Datei geöffnet, Aufrufe [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) Dokumentdaten zum Schreiben der Datei, und klicken Sie dann ein Dokument als bereinigen. Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung durch, wenn das Framework ein Dokument speichert ausführen möchten. Z. B. können Sie eine Anwendung schreiben, wobei Dokumente Datensätze in eine Datenbank statt in separaten Dateien darstellen.  
  
##  <a name="a-nameonunloadhandlera--cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 Wird vom Framework aufgerufen, wenn der Vorschauhandler entladen wird.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdatefilesendmaila--cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>CDocument:: OnUpdateFileSendMail  
 Ermöglicht die **ID_FILE_SEND_MAIL** -Befehl, wenn e-Mail-Unterstützung (MAPI) vorhanden ist.  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf die [CCmdUI](../../mfc/reference/ccmdui-class.md) zugeordnete Objekt der **ID_FILE_SEND_MAIL** Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion andernfalls entfernt der **ID_FILE_SEND_MAIL** Befehl über das Menü, einschließlich Trennzeichen, die oben oder unten im Menü Element entsprechend. MAPI ist aktiviert, wenn MAPI32. DLL ist in den Pfad und im Abschnitt [Mail] der Datei WIN. MAPI-INI-Datei =&1;. Die meisten Anwendungen werden mit diesem Befehl im Menü Datei abgelegt.  
  
 **CDocument** unterstützt das Dokument über e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="a-nameprecloseframea--cdocumentprecloseframe"></a><a name="precloseframe"></a>CDocument::PreCloseFrame  
 Diese Member-Funktion wird vom Framework aufgerufen, bevor das Rahmenfenster zerstört wird.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrame`  
 Zeiger auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) , enthält die zugeordnete **CDocument** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können überschrieben werden, um benutzerdefinierte bereinigen, aber Achten Sie darauf, dass Sie auch von der Basisklasse aufgerufen.  
  
 Der Standardwert von `PreCloseFrame` nichts **CDocument**. Die **CDocument**-abgeleitete Klassen [COleDocument](../../mfc/reference/coledocument-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) diese Memberfunktion.  
  
##  <a name="a-namereadnextchunkvaluea--cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 Liest den nächsten Block-Wert.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>Parameter  
 `ppValue`  
 [out] Bei Rückgabe der Funktion `ppValue` der gelesene Wert enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namereleasefilea--cdocumentreleasefile"></a><a name="releasefile"></a>CDocument::ReleaseFile  
 Diese Memberfunktion heißt vom Framework freigeben eine Datei, die von einer anderen Anwendung für die Verwendung zur Verfügung gestellt.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>Parameter  
 `pFile`  
 Ein Zeiger auf das CFile-Objekt, das freigegeben werden.  
  
 `bAbort`  
 Gibt an, ob die Datei freigegeben werden, indem Sie entweder `CFile::Close` oder `CFile::Abort`. **FALSE** ist die Datei freigegeben werden mithilfe von [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** ist die Datei freigegeben werden mithilfe von [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bAbort` ist **TRUE**, `ReleaseFile` Aufrufe `CFile::Abort`, und die Datei freigegeben ist. `CFile::Abort`wird keine Ausnahme ausgelöst.  
  
 Wenn `bAbort` ist **FALSE**, `ReleaseFile` Aufrufe `CFile::Close` und die Datei freigegeben ist.  
  
 Überschreiben Sie diese Memberfunktion, um eine Aktion durch den Benutzer erfordern, bevor die Datei freigegeben wird.  
  
##  <a name="a-nameremovechunka--cdocumentremovechunk"></a><a name="removechunk"></a>CDocument::RemoveChunk  
 Entfernt ein Segment mit der angegebenen GUID.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Parameter  
 `Guid`  
 Gibt die GUID eines entfernt werden soll.  
  
 `Pid`  
 Gibt die PID eines entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremoveviewa--cdocumentremoveview"></a><a name="removeview"></a>CDocument::RemoveView  
 Rufen Sie diese Funktion, um eine Ansicht aus einem Dokument zu trennen.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pView`  
 Verweist auf die Ansicht entfernt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion entfernt die angegebene Ansicht aus der Liste der Ansichten, die dem Dokument zugeordnet; Außerdem wird die Ansicht Dokument Zeiger auf **NULL**. Diese Funktion wird vom Framework aufgerufen, wenn ein Rahmenfenster geschlossen ist oder ein Bereich eines unterteilten Fensters geschlossen ist.  
  
 Rufen Sie diese Funktion nur, wenn Sie eine Ansicht manuell getrennt werden. In der Regel können Sie das Framework Trennen von Dokumenten und Ansichten durch die Definition einer [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt zuordnen einer Dokumentklasse Ansichtsklasse und Rahmenfenster (Klasse).  
  
 Beispiel finden Sie unter [AddView](#addview) für eine beispielimplementierung.  
  
##  <a name="a-namereportsaveloadexceptiona--cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 Wird aufgerufen, wenn eine Ausnahme ausgelöst wird (in der Regel eine [CFileException](../../mfc/reference/cfileexception-class.md) oder [CArchiveException](../../mfc/reference/carchiveexception-class.md)) beim Speichern oder Laden des Dokuments.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf den Namen des Dokuments, das wurde gespeichert oder geladen wird.  
  
 *e*  
 Verweist auf die Ausnahme, die ausgelöst wurde. Möglicherweise **NULL**.  
  
 *bSaving*  
 Ein Flag, der angibt, welcher Vorgang ausgeführt wurde; ungleich NULL, wenn das Dokument wurde gespeichert, 0, wenn beim Laden des Dokuments.  
  
 `nIDPDefault`  
 Bezeichner, der die Fehlermeldung, die angezeigt werden, wenn die Funktion eine spezifischere nicht angegeben ist.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des Ausnahmeobjekts untersucht und sucht nach eine Fehlermeldung angezeigt, die speziell auf die Ursache beschreibt. Wenn eine bestimmte Nachricht nicht gefunden wird oder wenn *e* ist **NULL**, die durch angegebene allgemeine Meldung der `nIDPDefault` Parameter verwendet wird. Die Funktion zeigt ein Meldungsfeld mit der Fehlermeldung. Überschreiben Sie diese Funktion, wenn Sie zusätzliche, benutzerdefinierte Fehlermeldungen bereitstellen möchten. Dies ist eine erweiterte überschrieben.  
  
##  <a name="a-namesavemodifieda--cdocumentsavemodified"></a><a name="savemodified"></a>SaveModified  
 Wird vom Framework aufgerufen, bevor ein geändertes Dokument geschlossen werden.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es sicherer ist, den Vorgang fortzusetzen, und schließen Sie das Dokument; 0, wenn das Dokument nicht geschlossen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion wird der Benutzer aufgefordert, ob die Änderungen auf das Dokument zu speichern, wenn alle vorgenommen wurden. Überschreiben Sie diese Funktion, wenn das Programm eine andere Abfrage Prozedur erforderlich. Dies ist eine erweiterte überschrieben.  
  
##  <a name="a-namesetchunkvaluea--cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>CDocument::SetChunkValue  
 Legt einen Block-Wert.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parameter  
 `pValue`  
 Gibt einen Block-Wert festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetmodifiedflaga--cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 Rufen Sie diese Funktion, nachdem Sie das Dokument in irgendeiner Weise vorgenommen haben.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Zeigt an, ob das Dokument geändert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Durch das Aufrufen dieser Funktion konsistent, stellen Sie sicher, dass das Framework der Benutzer vor dem Schließen eines Dokuments speichern kann. In der Regel sollten Sie den Standardwert verwenden **TRUE** für die `bModified` Parameter. Um ein Dokument wie bereinigen (unverändert) zu kennzeichnen, rufen Sie diese Funktion mit einem Wert von **FALSE**.  
  
##  <a name="a-namesetpathnamea--cdocumentsetpathname"></a><a name="setpathname"></a>CDocument::SetPathName  
 Rufen Sie diese Funktion, um den vollqualifizierten Pfad der Datei des Dokuments anzugeben.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf die Zeichenfolge, die als Pfad für das Dokument verwendet werden.  
  
 `bAddToMRU`  
 Bestimmt, ob der Dateiname hinzugefügt wird der zuletzt verwendeten Dateiliste (MRU) verwendete. Wenn **"TRUE"** der Dateiname hinzugefügt wird, wenn **FALSE**, nicht hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig vom Wert der `bAddToMRU` den Pfad hinzugefügt oder nicht hinzugefügt werden, um die Liste der zuletzt von der Anwendung verwaltet wird. Beachten Sie, dass einige Dokumente nicht mit einer externen Datei verknüpft sind. Rufen Sie diese Funktion nur, wenn Sie die standardmäßige Implementierung für das Öffnen und Speichern von Dateien, die vom Framework verwendete überschreiben.  
  
##  <a name="a-namesettitlea--cdocumentsettitle"></a><a name="settitle"></a>CDocument::SetTitle  
 Rufen Sie diese Funktion, um den Titel des Dokuments (die Zeichenfolge, die in der Titelleiste eines Rahmenfensters angezeigt) angeben.  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTitle`  
 Verweist auf die Zeichenfolge, die als Titel des Dokuments verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Funktion aktualisiert die Titel aller Frame-Fenster, in denen das Dokument angezeigt.  
  
##  <a name="a-nameupdateallviewsa--cdocumentupdateallviews"></a><a name="updateallviews"></a>UpdateAllViews  
 Rufen Sie diese Funktion aus, nachdem das Dokument geändert wurde.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pSender`  
 Verweist auf die Ansicht, die das Dokument geändert oder **NULL** alle Ansichten sind, aktualisiert werden.  
  
 `lHint`  
 Enthält Informationen über die Änderung.  
  
 `pHint`  
 Verweist auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten diese Funktion aufrufen, nach dem Aufruf der [SetModifiedFlag](#setmodifiedflag) Member-Funktion. Diese Funktion teilt jeder Ansicht, die mit dem Dokument, mit Ausnahme der angegebenen Ansicht verbunden `pSender`, die das Dokument geändert wurde. Rufen Sie in der Regel diese Funktion von der Ansichtsklasse, nachdem der Benutzer das Dokument über eine Sicht geändert hat.  
  
 Diese Funktion ruft die [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) Member-Funktion für jede der Ansichten außer den Versand des Dokuments anzuzeigen, das Übergeben von `pHint` und `lHint`. Verwenden Sie diese Parameter, Informationen zu den Ansichten zu Änderungen an das Dokument übergeben. Können Sie codieren, Informationen mit `lHint` und/oder können Sie definieren eine [CObject](../../mfc/reference/cobject-class.md)-abgeleiteten Klasse zum Speichern von Informationen zu den Änderungen, und übergeben Sie ein Objekt dieser Klasse mit `pHint`. Überschreiben der `CView::OnUpdate` Member-Funktion in Ihrer [CView](../../mfc/reference/cview-class.md)-abgeleitete Klasse, um die Aktualisierung der Ansicht angezeigt, die basierend auf den übergebenen Informationen zu optimieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#64;](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel NPP](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)

