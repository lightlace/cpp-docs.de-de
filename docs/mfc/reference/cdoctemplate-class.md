---
title: CDocTemplate-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
dev_langs: C++
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71d44aac1ca7a018be7be1b375dd92920af96dba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdoctemplate-class"></a>CDocTemplate-Klasse
Eine abstrakte Basisklasse, die die grundlegende Funktionalität für Dokumentvorlagen definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Erstellt ein `CDocTemplate`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|Fügt ein Dokument in eine Vorlage an.|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Schließt alle Dokumente, die mit dieser Vorlage verknüpft sind.|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Erstellt ein neues Dokument.|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|Erstellt ein neues Rahmenfenster mit einem Dokument und Ansicht an.|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|Erstellt ein OLE-fähigen Rahmenfenster.|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Erstellt einen untergeordneten Frame for Rich Preview verwendet.|  
|[CDocTemplate::GetDocString](#getdocstring)|Ruft eine Zeichenfolge, die den Dokumenttyp zugeordnet.|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Ruft die Position des ersten dieser Vorlage zugeordneten Dokuments ab.|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|Ruft ein Dokument und die Position des nächsten ab.|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Initialisiert das Rahmenfenster und optional sichtbar macht.|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|Lädt die Ressourcen für einen bestimmten `CDocTemplate` oder eine abgeleitete Klasse.|  
|[CDocTemplate::MatchDocType](#matchdoctype)|Bestimmt den Grad an Vertrauen der Übereinstimmung zwischen einem Dokument und diese Vorlage an.|  
|[CDocTemplate:: OpenDocumentFile](#opendocumentfile)|Öffnet eine Datei, die durch ein Pfadname angegeben.|  
|[CDocTemplate::RemoveDocument](#removedocument)|Entfernt ein Dokument aus einer Vorlage an.|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|Speichert alle Dokumente dieser Vorlage zugeordneten bearbeitet wurden.|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Bestimmt, die Ressourcen für OLE-Container bei einem direkten OLE-Element zu bearbeiten.|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Zeigt den Standardtitel in der Titelleiste des Dokumentfensters.|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Vorschau für Installationen außerhalb des Prozesses.|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|Bestimmt die Ressourcen und Klassen, wenn das Serverdokument eingebettet oder direktes bearbeitet.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie in der Regel eine oder mehrere Dokumentvorlagen in der Implementierung Ihrer Anwendung `InitInstance` Funktion. Eine Dokumentvorlage definiert die Beziehungen zwischen drei Typen von Klassen:  
  
-   Eine Dokumentenklasse, die Ableitung von **CDocument**.  
  
-   Eine View-Klasse, die Daten aus den oben aufgeführten Dokumentklasse anzeigt. Sie können diese Klasse von ableiten `CView`, `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für eine einzelnes Dokument Interface (SDI)-Anwendung, leiten Sie diese Klasse von `CFrameWnd`. Für eine Anwendung multiple Document Interface (MDI), leiten Sie diese Klasse von `CMDIChildWnd`. Wenn Sie zum Anpassen des Verhaltens des Rahmenfensters benötigen, können Sie `CFrameWnd` oder `CMDIChildWnd` direkt, ohne eine eigene Klasse ableiten.  
  
 Die Anwendung verfügt eine Dokumentvorlage für jeden Typ von Dokument, die dies unterstützt. Wenn Ihre Anwendung Kalkulationstabellen und Textdokumente unterstützt, muss die Anwendung z. B. zwei Dokument Vorlagenobjekte. Jedes Dokumentvorlage dient zum Erstellen und verwalten alle Dokumente dieses Typs.  
  
 Die Dokumentvorlage speichert Zeiger auf die `CRuntimeClass` Objekte für das Dokument anzeigen und Klassen für Rahmenfenster. Diese `CRuntimeClass` Objekte werden angegeben, wenn eine Dokumentvorlage zu erstellen.  
  
 Das Dokumentvorlage enthält die ID der Ressourcen, mit dem Dokumenttyp (z. B. Menüs, Symbol oder tabellenressourcen Zugriffstaste) verwendet. Die Dokumentvorlage verfügt auch über Zeichenfolgen, die zusätzliche Informationen zu den Dokumenttyp enthält. Dazu gehören der Name der der Dokumenttyp (z. B. "Tabelle") und die Dateierweiterung (z. B. ".xls"). Optional können sie andere Zeichenfolgen, die von der Benutzeroberfläche der Anwendung, die Windows-Manager für Dateiserver und Object Linking and Embedding (OLE)-Unterstützung verwendet enthalten.  
  
 Wenn Ihre Anwendung ein OLE-Container bzw. der Server ist, definiert die Dokumentvorlage auch die ID des Menüs während der direkten Aktivierung verwendet. Wenn Ihre Anwendung einen OLE-Server ist, definiert der Dokumentvorlage die ID der Symbolleiste und Menüs, die während der direkten Aktivierung verwendet. Sie geben diese zusätzlichen OLE-Ressourcen durch Aufrufen von `SetContainerInfo` und `SetServerInfo`.  
  
 Da `CDocTemplate` ist eine abstrakte Klasse, Sie können die Klasse nicht direkt verwenden. Eine typische Anwendung verwendet einen der beiden `CDocTemplate`-abgeleitete Klassen, die von der Microsoft Foundation Class-Bibliothek bereitgestellt: `CSingleDocTemplate`, SDI, implementiert und `CMultiDocTemplate`, MDI implementiert. Finden Sie diese Klassen für Weitere Informationen zur Verwendung von Dokumentvorlagen.  
  
 Wenn Ihre Anwendung eine Sichtweise der Benutzeroberfläche, die grundlegend von SDI- oder MDI-ist erfordert, leiten Sie eine eigene Klasse von `CDocTemplate`.  
  
 Weitere Informationen zu `CDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="adddocument"></a>CDocTemplate::AddDocument  
 Verwenden Sie diese Funktion, um ein Dokument in eine Vorlage hinzufügen.  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Ein Zeiger auf das Dokument hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die abgeleiteten Klassen [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) und [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) überschreiben diese Funktion. Wenn Sie eine eigene Klasse Dokumentvorlagen von ableiten `CDocTemplate`, die abgeleitete Klasse muss diese Funktion überschreiben.  
  
##  <a name="cdoctemplate"></a>CDocTemplate::CDocTemplate  
 Erstellt ein `CDocTemplate`-Objekt.  
  
```  
CDocTemplate (
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDResource`  
 Gibt die ID der Ressourcen, mit dem Dokument verwendet. Dies kann im Menü, Symbol Zugriffstastentabelle und Zeichenfolgenressourcen umfassen.  
  
 Eine Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, getrennt durch das Zeichen "\n" (das Zeichen "\n" ist als Platzhalter erforderlich, wenn eine Teilzeichenfolge nicht angegeben wird; nachfolgende "\n"-Zeichen sind jedoch nicht erforderlich) Diese Teilzeichenfolgen beschreiben den "Document". Informationen zu den Teilzeichenfolgen, finden Sie unter [GetDocString](#getdocstring). Diese Zeichenfolgenressource in der Ressourcendatei für die Anwendung gefunden. Zum Beispiel:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Beachten Sie, dass die Zeichenfolge mit einem "\n"-Zeichen beginnt. Dies ist, da die erste Teilzeichenfolge für MDI-Anwendungen nicht verwendet wird und daher nicht enthalten ist. Sie können diese Zeichenfolge mit der Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in Zeichenfolgen-Editor nicht als sieben trennen Sie die Einträge angezeigt.  
  
 `pDocClass`  
 Verweist auf die `CRuntimeClass` Objekt der Dokumentklasse. Diese Klasse ist eine **CDocument**-abgeleitete Klasse, die Sie definieren, um Ihre Dokumente darzustellen.  
  
 `pFrameClass`  
 Verweist auf die `CRuntimeClass` Objekt von der Rahmenfenster (Klasse). Diese Klasse kann eine `CFrameWnd`-abgeleitete Klasse, oder es kann `CFrameWnd` selbst, wenn Sie Standardverhalten für das Hauptrahmenfenster verwenden möchten.  
  
 `pViewClass`  
 Verweist auf die `CRuntimeClass` Objekt der Ansichtsklasse. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie definieren, um Ihre Dokumente anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion zum Erstellen einer `CDocTemplate` Objekt. Dynamisch Zuordnen einer `CDocTemplate` Objekt, und übergeben Sie sie an [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) aus der `InitInstance` Memberfunktion Ihrer Anwendung-Klasse.  
  
##  <a name="closealldocuments"></a>CDocTemplate::CloseAllDocuments  
 Rufen Sie diese Memberfunktion zum Schließen aller geöffneten Dokumente.  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parameter  
 `bEndSession`  
 Gibt an, und zwar unabhängig davon, ob die Sitzung beendet wird. Es ist **"true"** wird die Sitzung beendet wird andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird in der Regel als Teil der Datei Exit-Befehl verwendet. Ruft die standardmäßige Implementierung dieser Funktion die [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) Memberfunktion So löschen Sie des Dokuments Daten und schließt dann die Rahmenfenster für alle Ansichten, die mit dem Dokument verknüpft.  
  
 Überschreiben Sie diese Funktion ggf. erforderlich, dass der Benutzer Verarbeitungsschritte spezielle Bereinigung ausführen, bevor das Dokument geschlossen wird. Wenn das Dokument einen Datensatz in einer Datenbank darstellt, sollten Sie dieser Funktion können Sie die Datenbank schließen, außer Kraft setzen.  
  
##  <a name="createnewdocument"></a>CDocTemplate::CreateNewDocument  
 Rufen Sie diese Memberfunktion zum Erstellen eines neuen Dokuments des Typs, der mit dieser Dokumentvorlage.  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das gerade erstellte Dokument oder **NULL** Wenn ein Fehler auftritt.  
  
##  <a name="createnewframe"></a>CDocTemplate::CreateNewFrame  
 Erstellt ein neues Rahmenfenster mit einem Dokument und Ansicht an.  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Das Dokument, das neue Rahmenfenster verweisen soll. Kann **NULL**.  
  
 `pOther`  
 Das Rahmenfenster, auf dem das neue Rahmenfenster ist, basieren soll. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Rahmenfenster oder **NULL** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 `CreateNewFrame`verwendet die `CRuntimeClass` Objekte an den Konstruktor beim Erstellen eines neuen Frame-Fensters mit einer Ansicht und angefügtes Dokument übergeben. Wenn die `pDoc` Parameter ist **NULL**, das Framework gibt eine Ablaufverfolgungsmeldung.  
  
 Die `pOther` Parameter wird verwendet, um den neuen Fenster Befehl zu implementieren. Er enthält ein Rahmenfensters auf dem das neue Rahmenfenster zu modellieren. Normalerweise wird das neue Rahmenfenster unsichtbar erstellt. Mit dieser Funktion wird zum Erstellen von Rahmenfenster außerhalb der standard-Framework-Implementierung der neuen Datei und die Datei öffnen.  
  
##  <a name="createoleframe"></a>CDocTemplate::CreateOleFrame  
 Erstellt ein OLE-Rahmenfenster.  
  
```  
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc,  
    BOOL bCreateView);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf den Frame des übergeordneten Fensters.  
  
 `pDoc`  
 Ein Zeiger auf das Dokument, das das neue OLE-Rahmenfenster verweisen soll.  
  
 `bCreateView`  
 Bestimmt, ob eine Sicht zusammen mit den Frame erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Framefenster bei Erfolg; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bCreateView` NULL ist, ein leerer Frame wird erstellt.  
  
##  <a name="getdocstring"></a>CDocTemplate::GetDocString  
 Ruft eine Zeichenfolge, die den Dokumenttyp zugeordnet.  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rString`  
 Ein Verweis auf eine `CString` -Objekt, das die Zeichenfolge enthalten soll, wenn die Funktion zurückgibt.  
  
 *Index*  
 Ein Index der Teilzeichenfolge, die aus der Zeichenfolge, die den Dokumenttyp beschreibt abgerufen wird. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- **CDocTemplate::windowTitle** Name, in das Anwendungsfenster Titelleiste (z. B. "Microsoft Excel") angezeigt wird. Nur in der Dokumentvorlage für SDI-Anwendungen enthalten.  
  
- **CDocTemplate::docName** Stamms für die der Name des Standarddokuments (z. B. "Blatt"). Diesen Stamm plus eine Zahl ist, wird für den Standardnamen, der ein neues Dokument dieses Typs verwendet, wenn der Benutzer über das Menü Datei (z. B. "Sheet1" oder "Sheet2") den neuen Befehl auswählt. Wenn nicht angegeben ist, wird "Unbenannt" als Standard verwendet.  
  
- **CDocTemplate:: fileNewName entspricht** Name für diesen Dokumenttyp. Wenn die Anwendung mehr als ein Typ des Dokuments unterstützt, wird diese Zeichenfolge in das Dialogfeld neue Datei (z. B. "Tabelle") angezeigt. Wenn nicht angegeben, wird der Dokumenttyp kann nicht zugegriffen werden mit dem Befehl neue Datei.  
  
- **CDocTemplate::filterName** Beschreibung für den Dokumenttyp und einen Platzhalterfilter, die übereinstimmende Dokumente dieses Typs. Diese Zeichenfolge wird in der Liste Dateityp Dropdown-Liste im Dialogfeld Datei öffnen (z. B. "Arbeitsblätter (*.xls)") angezeigt. Wenn nicht angegeben, ist der Dokumenttyp nicht zugegriffen werden, kann mithilfe des Befehls Datei öffnen.  
  
- **CDocTemplate::filterExt** -Erweiterung für Dokumente dieses Typs (z. B. ".xls"). Wenn nicht angegeben, ist der Dokumenttyp nicht zugegriffen werden, kann mithilfe des Befehls Datei öffnen.  
  
- **CDocTemplate::regFileTypeId** Bezeichner für den Dokumenttyp, der in der Registrierungsdatenbank beibehalten von Windows gespeichert werden. Bei dieser Zeichenfolge wird nur zur internen Verwendung (z. B. "ExcelWorksheet"). Wenn nicht angegeben ist, kann der Dokumenttyp mit dem Windows-Datei-Manager registriert werden.  
  
- **CDocTemplate::regFileTypeName** Name des Dokumenttyps in der Registrierungsdatenbank gespeichert werden. Diese Zeichenfolge kann in Dialogfeldern von Anwendungen angezeigt werden, die Zugriff auf die Registrierungsdatenbank (z. B. "Microsoft Excel-Arbeitsblatt").  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die angegebene Teilzeichenfolge gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen einer bestimmten Teilzeichenfolge, die den Dokumenttyp beschreibt. Die Zeichenfolge, enthält diese Teilzeichenfolgen in das Dokumentvorlage gespeichert wird und stammt aus einer Zeichenfolge in der Ressourcendatei für die Anwendung. Das Framework ruft diese Funktion zum Abrufen von Zeichenfolgen für die Benutzeroberfläche der Anwendung benötigten. Wenn Sie eine Dateinamenerweiterung für Dokumente für Ihre Anwendung angegeben haben, ruft das Framework auch diese Funktion beim Hinzufügen eines Eintrags in die Windows-Registrierungsdatenbank; Dadurch können Dokumente aus den Windows-Datei-Manager geöffnet werden.  
  
 Mit dieser Funktion wird nur dann, wenn Sie eine eigene Klasse von ableiten, werden `CDocTemplate`.  
  
##  <a name="getfirstdocposition"></a>CDocTemplate::GetFirstDocPosition  
 Ruft die Position des ersten dieser Vorlage zugeordneten Dokuments ab.  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der zum Durchlaufen der Liste der Dokumente dieser Dokumentvorlage; zugeordneten verwendet werden kann oder **NULL** , wenn die Liste leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Position des ersten Dokuments in der Liste der Dokumente, die dieser Vorlage zugeordneten abzurufen. Verwenden der **POSITION** Wert als Argument an [CDocTemplate::GetNextDoc](#getnextdoc) zum Durchlaufen der Liste der Dokumente, die der Vorlage zugeordnet.  
  
 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) und [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) überschreiben diese rein virtuelle Funktion. Jede Klasse, von ableiten `CDocTemplate` müssen diese Funktion auch überschreiben.  
  
##  <a name="getnextdoc"></a>CDocTemplate::GetNextDoc  
 Ruft das Listenelement identifizierten `rPos`, legt dann `rPos` auf die **POSITION** Wert, der den nächsten Eintrag in der Liste.  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Dokument in der Liste der Dokumente, die mit dieser Vorlage verknüpft sind.  
  
### <a name="parameters"></a>Parameter  
 `rPos`  
 Ein Verweis auf eine **POSITION** durch einen vorherigen Aufruf zurückgegebene Wert [GetFirstDocPosition](#getfirstdocposition) oder `GetNextDoc`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das abgerufene Element das letzte Element in der Liste klicken Sie dann der neue Wert des `rPos` festgelegt ist, um **NULL**.  
  
 Sie können `GetNextDoc` in einer Schleife vorwärts, wenn Sie die erste Position mit einem Aufruf von einrichten [GetFirstDocPosition](#getfirstdocposition).  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert stellt eine gültige Position in der Liste dar. Wenn er ungültig ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek.  
  
##  <a name="initialupdateframe"></a>CDocTemplate::InitialUpdateFrame  
 Initialisiert das Rahmenfenster und optional sichtbar macht.  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrame`  
 Das Rahmenfenster, das das ursprüngliche Update benötigt.  
  
 `pDoc`  
 Das Dokument, das der Frame zugeordnet ist. Kann **NULL**.  
  
 `bMakeVisible`  
 Gibt an, ob der Frame angezeigt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **IntitialUpdateFrame** nach dem Erstellen eines neuen Frames mit dem `CreateNewFrame`. Das Aufrufen dieser Funktion führt dazu, dass die Ansichten in diesem Fenster Frame zum Empfangen von ihren `OnInitialUpdate` aufrufen. Außerdem war es nicht bereits eine aktive Ansicht, die Hauptansicht des Rahmenfensters active erfolgt; die primäre Ansicht ist eine Ansicht mit der ID untergeordneten **AFX_IDW_PANE_FIRST**. Schließlich wird das Rahmenfenster sichtbar gemacht Wenn `bMakeVisible` ungleich NULL ist. Wenn `bMakeVisible` ist 0 (null), wird der aktuelle Fokus und sichtbaren Zustand des Rahmenfensters bleiben jedoch unverändert.  
  
 Es ist nicht notwendig, diese Funktion aufrufen, wenn das Framework-Implementierung der neuen Datei und die Datei öffnen zu verwenden.  
  
##  <a name="loadtemplate"></a>CDocTemplate::LoadTemplate  
 Lädt die Ressourcen für einen bestimmten `CDocTemplate` oder eine abgeleitete Klasse.  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion aufgerufen wird, durch das Framework beim Laden der Ressourcen für einen bestimmten `CDocTemplate` oder eine abgeleitete Klasse. Normalerweise wird er während der Erstellung außer aufgerufen, wenn die Vorlage, Global erstellt wird. In diesem Fall wird der Aufruf von `LoadTemplate` wird verzögert, bis [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) aufgerufen wird.  
  
##  <a name="matchdoctype"></a>CDocTemplate::MatchDocType  
 Bestimmt den Grad an Vertrauen der Übereinstimmung zwischen einem Dokument und diese Vorlage an.  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Der Pfadname der Datei an, dessen Typ bestimmt werden soll.  
  
 `rpDocMatch`  
 Zeiger auf ein Dokument, das das übereinstimmende Dokument zugeordnet ist, wenn die Datei durch angegeben `lpszPathName` ist bereits geöffnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der **vertrauen** -Enumeration, die wie folgt definiert ist:  
  
```  
enum Confidence  
    {  
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion zum Bestimmen des Typs der Dokumentvorlage zum Öffnen einer Datei verwendet werden soll. Wenn Ihre Anwendung mehrere Dateitypen unterstützt werden, z. B. können diese Funktion um zu bestimmen, welche der verfügbaren Vorlagen für eine bestimmte Datei durch den Aufruf eignet `MatchDocType` für jede Vorlage im aktivieren, und beim Auswählen einer Vorlage entsprechend dem der Vertrauensgrad-Wert zurückgegeben.  
  
 Wenn die Datei durch angegeben `lpszPathName` ist bereits geöffnet ist, gibt diese Funktion **CDocTemplate::yesAlreadyOpen** und kopiert die Datei **CDocument** Objekt in das Objekt am `rpDocMatch`.  
  
 Ist die Datei nicht geöffnet ist, aber die Erweiterung in `lpszPathName` entspricht die Erweiterung gemäß **CDocTemplate::filterExt**, gibt diese Funktion **CDocTemplate::yesAttemptNative** und legt `rpDocMatch` auf **NULL**. Weitere Informationen zu **CDocTemplate::filterExt**, finden Sie unter [CDocTemplate::GetDocString](#getdocstring).  
  
 Wenn weder Fall auf "true" festgelegt ist, gibt die Funktion **CDocTemplate::yesAttemptForeign**.  
  
 Die Standardimplementierung gibt keinen zurück **CDocTemplate::maybeAttemptForeign** oder **CDocTemplate::maybeAttemptNative**. Überschreiben Sie diese Funktion, um für Ihre Anwendung, die vielleicht mit dieser beiden Werte von geeigneten Typ übereinstimmende Logik implementieren die **vertrauen** Enumeration.  
  
##  <a name="opendocumentfile"></a>CDocTemplate:: OpenDocumentFile  
 Öffnet eine Datei, die durch einen Pfad angegeben.  
  
```  
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;  
 
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPathName`  
 Ein Zeiger auf den Pfad der Datei, die das Dokument geöffnet werden.  
  
 [in] `bAddToMRU`  
 `TRUE`Gibt an, dass das Dokument ist eine der letzten Dateien. `FALSE` gibt an, das Dokument ist nicht die aktuellsten Dateien.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, dessen Datei von heißt `lpszPathName`; `NULL` Wenn Fehler auftreten.  
  
### <a name="remarks"></a>Hinweise  
 Öffnet die Datei, deren Pfad gemäß `lpszPathName`. Wenn `lpszPathName` ist `NULL`, eine neue Datei, die ein Dokument des Typs, der mit dieser Vorlage erstellt wird.  
  
##  <a name="removedocument"></a>CDocTemplate::RemoveDocument  
 Entfernt das Dokument verweist `pDoc` aus der Liste der Dokumente, die mit dieser Vorlage verknüpft sind.  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Ein Zeiger auf das Dokument entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die abgeleiteten Klassen `CMultiDocTemplate` und `CSingleDocTemplate` überschreiben diese Funktion. Wenn Sie eine eigene Klasse Dokumentvorlagen von ableiten `CDocTemplate`, die abgeleitete Klasse muss diese Funktion überschreiben.  
  
##  <a name="saveallmodified"></a>CDocTemplate::SaveAllModified  
 Speichert alle Dokumente, die geändert wurden.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich; andernfalls 0.  
  
##  <a name="setcontainerinfo"></a>CDocTemplate::SetContainerInfo  
 Bestimmt, die Ressourcen für OLE-Container bei einem direkten OLE-Element zu bearbeiten.  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDOleInPlaceContainer`  
 Die ID der Ressourcen verwendet werden, wenn ein eingebettetes Objekt aktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Festlegen der Ressourcen verwendet werden, wenn ein OLE-Objekt aktiviert ist. Diese Ressourcen gehören die Menüs und Zugriffstastentabellen. Diese Funktion wird in der Regel aufgerufen, der [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Funktion Ihrer Anwendung.  
  
 Klicken Sie im Menü zugeordneten `nIDOleInPlaceContainer` enthält Trennzeichen, die im Menü des aktivierten direktes-Elements, das Zusammenführen mit dem Menü des Steuerelementcontainer-Anwendung zu ermöglichen. Weitere Informationen über das Zusammenführen von Menüs für Server und-Container finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="setdefaulttitle"></a>CDocTemplate::SetDefaultTitle  
 Mit dieser Funktion wird zum Laden des Dokuments Standardtitel und zeigt sie auf der Titelleiste des Dokuments.  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *pDocument*  
 Ein Zeiger auf das Dokument, deren Titel festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu den Standardtitel, finden Sie unter der Beschreibung der **CDocTemplate::docName** in [CDocTemplate::GetDocString](#getdocstring).  
  
##  <a name="setserverinfo"></a>CDocTemplate::SetServerInfo  
 Bestimmt die Ressourcen und Klassen, wenn das Serverdokument eingebettet oder direktes bearbeitet.  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDOleEmbedding*  
 Die ID der Ressourcen verwendet werden, wenn ein eingebettetes Objekt in einem separaten Fenster geöffnet wird.  
  
 `nIDOleInPlaceServer`  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt ist aktiviert, direkte.  
  
 *pOleFrameClass*  
 Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur, die Klasseninformationen für die Frame-Fensterobjekt erstellt, wenn direkte Aktivierung auftritt enthält.  
  
 *pOleViewClass*  
 Zeiger auf eine `CRuntimeClass` Struktur, die Klasseninformationen für das Ansichtsobjekt erstellt, wenn direkte Aktivierung auftritt enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Identifizieren der Ressourcen, die von der Serveranwendung verwendet wird, wenn der Benutzer die Aktivierung eines eingebetteten Objekts anfordert. Diese Ressourcen umfassen Menüs und Zugriffstastentabellen. Diese Funktion wird in der Regel aufgerufen, der `InitInstance` Ihrer Anwendung.  
  
 Klicken Sie im Menü zugeordneten `nIDOleInPlaceServer` Trennzeichen, mit denen im Menü "Server" zum Zusammenführen mit dem Menü des Containers enthält. Weitere Informationen über das Zusammenführen von Menüs für Server und-Container finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="createpreviewframe"></a>CDocTemplate::CreatePreviewFrame  
 Erstellt einen untergeordneten Frame for Rich Preview verwendet.  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf ein übergeordnetes Fenster (normalerweise von der Shell bereitgestellt).  
  
 `pDoc`  
 Ein Zeiger auf ein Document-Objekt zurück, deren Inhalt werden in der Vorschau angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf eine `CFrameWnd` -Objekt, oder `NULL` Wenn die Erstellung fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpreviewinfo"></a>CDocTemplate::SetPreviewInfo  
 Richtet die Out-of Prozess Preview Handler.  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDPreviewFrame`  
 Gibt eine Ressourcen-ID des Frames Vorschau an.  
  
 `pPreviewFrameClass`  
 Gibt einen Zeiger auf eine Common Language Runtime Informationen Klassenstruktur des Frames Vorschau an.  
  
 `pPreviewViewClass`  
 Gibt einen Zeiger auf eine Common Language Runtime Informationen Klassenstruktur von der Vorschauansicht an.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate-Klasse](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate-Klasse](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CScrollView-Klasse](../../mfc/reference/cscrollview-class.md)   
 [CEditView-Klasse](../../mfc/reference/ceditview-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)
