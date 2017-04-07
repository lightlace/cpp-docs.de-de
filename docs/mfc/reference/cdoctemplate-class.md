---
title: CDocTemplate-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- document templates
- templates, document
- CDocTemplate class
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
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
ms.openlocfilehash: 56ad45a061986c320e14054a2c77683cb5d89ac2
ms.lasthandoff: 02/24/2017

---
# <a name="cdoctemplate-class"></a>CDocTemplate-Klasse
Eine abstrakte Basisklasse, die die grundlegende Funktionalität für Dokumentvorlagen definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Erstellt ein `CDocTemplate`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|Eine Vorlage für hinzugefügt ein Dokument.|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Schließt alle Dokumente, die mit dieser Vorlage verknüpft sind.|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Erstellt ein neues Dokument.|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|Erstellt ein neues Rahmenfenster mit einem Dokument und Ansicht.|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|Erstellt ein OLE-fähige Rahmenfenster.|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Erstellt einen untergeordneten Frame for Rich Preview verwendet.|  
|[CDocTemplate::GetDocString](#getdocstring)|Ruft eine Zeichenfolge mit dem Dokument verknüpft ist.|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Ruft die Position des ersten dieser Vorlage zugeordneten Dokuments ab.|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|Ruft ein Dokument und die Position des nächsten ab.|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Initialisiert das Rahmenfenster und optional eingeblendet.|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|Lädt die Ressourcen für eine bestimmte `CDocTemplate` oder eine abgeleitete Klasse.|  
|[CDocTemplate::MatchDocType](#matchdoctype)|Bestimmt das Maß an Vertrauen in die Übereinstimmung zwischen einem Dokumenttyp und diese Vorlage.|  
|[CDocTemplate:: OpenDocumentFile](#opendocumentfile)|Öffnet eine Datei, die durch ein Pfadname angegeben.|  
|[CDocTemplate::RemoveDocument](#removedocument)|Entfernt ein Dokument aus einer Vorlage.|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|Speichert alle Dokumente dieser Vorlage zugeordneten bearbeitet wurden.|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Bestimmt, welche Ressourcen für die OLE-Container bei einem direkten OLE-Element zu bearbeiten.|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Zeigt den Standardtitel in der Titelleiste des Dokumentfensters.|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Vorschau für Installationen außerhalb des Prozesses.|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|Wenn das Serverdokument eingebettet oder direktes bearbeitet die Ressourcen und Klassen bestimmt werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie in der Regel eine oder mehrere Dokumentvorlagen in der Implementierung Ihrer Anwendung `InitInstance` Funktion. Eine Dokumentvorlage definiert die Beziehungen zwischen drei Typen von Klassen:  
  
-   Eine Dokumentenklasse, die Ableitung von **CDocument**.  
  
-   Eine View-Klasse, die Daten aus der oben aufgeführten Dokumentklasse anzeigt. Sie können diese Klasse von ableiten `CView`, `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für ein einzelnes Dokument Interface (SDI)-Anwendung, leiten Sie diese Klasse von `CFrameWnd`. Für eine Anwendung multiple Document Interface (MDI), leiten Sie diese Klasse von `CMDIChildWnd`. Wenn Sie zum Anpassen des Verhaltens des Rahmenfensters benötigen, können Sie `CFrameWnd` oder `CMDIChildWnd` direkt, ohne eine eigene Klasse ableiten.  
  
 Ihre Anwendung hat eine Dokumentvorlage für jeden Typ von Dokument, das es unterstützt. Wenn Ihre Anwendung Tabellen und Dokumente unterstützt, muss die Anwendung z. B. zwei Document Template-Objekten. Jede Dokumentvorlage ist verantwortlich für das Erstellen und Verwalten aller Dokumente des Typs.  
  
 Die Dokumentvorlage speichert Zeiger auf die `CRuntimeClass` Objekte für das Dokument, die Ansicht und die Rahmenfensterklassen. Diese `CRuntimeClass` Objekte werden angegeben, wenn Sie eine Dokumentvorlage erstellen.  
  
 Die Dokumentvorlage enthält die ID der mit dem Dokument (z. B. Menüs, Symbol oder Accelerator tabellenressourcen) verwendeten Ressourcen. Die Dokumentvorlage verfügt auch über Zeichenfolgen, die zusätzliche Informationen zu den Dokumenttyp enthält. Dazu gehören der Name des Dokumenttyps (z. B. "Tabelle") und die Erweiterung (z. B. ".xls"). Optional können sie andere Zeichenfolgen, die von der Benutzeroberfläche der Anwendung, die Windows-Datei-Manager, und Object Linking and Embedding (OLE)-Unterstützung verwendet enthalten.  
  
 Wenn Ihre Anwendung ein OLE-Container bzw. der Server ist, definiert die Dokumentvorlage auch die ID des Menüs während der direkten Aktivierung verwendet. Wenn Ihre Anwendung einen OLE-Server ist, definiert die Dokumentvorlage die ID der Symbolleiste und im Menü während der direkten Aktivierung verwendet. Geben Sie diese zusätzlichen OLE-Ressourcen durch Aufrufen `SetContainerInfo` und `SetServerInfo`.  
  
 Da `CDocTemplate` ist eine abstrakte Klasse, die-Klasse kann nicht direkt verwendet. Eine normale Anwendung verwendet eine der beiden `CDocTemplate`-abgeleitete Klassen, die von der Microsoft Foundation Class-Bibliothek bereitgestellt: `CSingleDocTemplate`, SDI, implementiert und `CMultiDocTemplate`, MDI implementiert. Finden Sie diese Klassen für Weitere Informationen zur Verwendung von Dokumentvorlagen.  
  
 Wenn Ihre Anwendung eine Sichtweise der Benutzeroberfläche, die grundlegend von SDI- oder MDI-ist erfordert, leiten Sie eine eigene Klasse von `CDocTemplate`.  
  
 Weitere Informationen zu `CDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokument und Ansicht](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="adddocument"></a>CDocTemplate::AddDocument  
 Verwenden Sie diese Funktion zum Hinzufügen eines Dokuments mit einer Vorlage.  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Ein Zeiger auf das Dokument hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die abgeleiteten Klassen [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) und [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) überschreiben. Wenn Sie eine eigene Klasse Dokumentvorlagen von ableiten `CDocTemplate`, die abgeleitete Klasse muss diese Funktion überschreibt.  
  
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
 Gibt die ID der mit dem Dokumenttyp verwendeten Ressourcen. Dies kann im Menü, Symbol, Zugriffstastentabelle und Zeichenfolgenressourcen enthalten.  
  
 Die Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, die durch das Zeichen '\n' getrennte (das Zeichen '\n' wird als Platzhalter benötigt, wenn eine Teilzeichenfolge nicht enthalten ist; nachfolgende '\n'-Zeichen sind jedoch nicht erforderlich) Diese Teilzeichenfolgen beschreiben den Dokumenttyp. Informationen zu den Teilzeichenfolgen, finden Sie unter [GetDocString](#getdocstring). Diese Zeichenfolgenressource befindet sich in der Ressourcendatei der Anwendung. Zum Beispiel:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Beachten Sie, dass die Zeichenfolge mit dem Zeichen '\n' beginnt. Dies ist die erste Teilzeichenfolge wird nicht für MDI-Anwendung verwendet und ist daher nicht enthalten. Sie können diese Zeichenfolge im Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in der Zeichenfolgen-Editor nicht als sieben separate Einträge angezeigt.  
  
 `pDocClass`  
 Verweist auf die `CRuntimeClass` Objekt der Document-Klasse. Diese Klasse ist eine **CDocument**-abgeleitete Klasse, die Sie zur Darstellung von Dokumenten definieren.  
  
 `pFrameClass`  
 Verweist auf die `CRuntimeClass` Objekt das Rahmenfenster (Klasse). Diese Klasse kann eine `CFrameWnd`-abgeleitete Klasse, oder es kann `CFrameWnd` selbst, wenn Sie Standardverhalten für das Hauptrahmenfenster verwenden möchten.  
  
 `pViewClass`  
 Verweist auf die `CRuntimeClass` Objekt der Klasse anzeigen. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie zur Anzeige von Dokumenten definieren.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion zum Erstellen einer `CDocTemplate` Objekt. Dynamisch eine `CDocTemplate` Objekt und übergeben es an [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) aus der `InitInstance` -Memberfunktion der Anwendungsklasse.  
  
##  <a name="closealldocuments"></a>CDocTemplate::CloseAllDocuments  
 Rufen Sie diese Memberfunktion zum Schließen aller geöffneten Dokumente.  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parameter  
 `bEndSession`  
 Gibt an, ob die Sitzung beendet wird. Es ist **TRUE** wird die Sitzung beendet wird andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird in der Regel als Teil des Befehls beenden verwendet. Ruft die standardmäßige Implementierung dieser Funktion die [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) Memberfunktion zum Löschen des Dokuments Daten und schließt dann das Rahmenfenster für alle Ansichten an das Dokument angefügt.  
  
 Überschreiben Sie diese Funktion, wenn der Benutzer Verarbeitungsschritte spezielle Bereinigung vor dem Schließen des Dokuments werden soll. Z. B. wenn das Dokument einen Datensatz in einer Datenbank darstellt, können Sie diese Funktion, um die Datenbank zu schließen überschreiben möchten.  
  
##  <a name="createnewdocument"></a>CDocTemplate::CreateNewDocument  
 Rufen Sie diese Memberfunktion zum Erstellen eines neuen Dokuments, der den Typ dieser Dokumentvorlage zugeordnet.  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Dokument oder **NULL** , wenn ein Fehler auftritt.  
  
##  <a name="createnewframe"></a>CDocTemplate::CreateNewFrame  
 Erstellt ein neues Rahmenfenster mit einem Dokument und Ansicht.  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Das Dokument, das das neue Rahmenfenster verweisen soll. Kann **NULL**.  
  
 `pOther`  
 Das Rahmenfenster, auf dem das neue Rahmenfenster ist, basieren soll. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Rahmenfenster oder **NULL** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 `CreateNewFrame`verwendet die `CRuntimeClass` Objekte an den Konstruktor übergeben, erstellen ein neues Rahmenfenster mit einer Ansicht und das Dokument angefügt. Wenn die `pDoc` Parameter ist **NULL**, das Framework wird eine Meldung ausgegeben.  
  
 Die `pOther` Parameter wird verwendet, um das Fenster neue Befehl zu implementieren. Es stellt ein Rahmenfenster auf dem Modell neue Rahmenfenster. Das neue Rahmenfenster ist normalerweise unsichtbar erstellt. Rufen Sie diese Funktion zum Erstellen von Rahmenfenstern außerhalb der standard-Framework-Implementierung von Datei auf neu und öffnen.  
  
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
 Ein Zeiger auf den Rand des übergeordneten Fensters.  
  
 `pDoc`  
 Ein Zeiger auf das Dokument, das das neue OLE-Rahmenfenster verweisen soll.  
  
 `bCreateView`  
 Bestimmt, ob eine Sicht, zusammen mit den Frame erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Rahmenfenster, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bCreateView` NULL ist, ein leerer Frame wird erstellt.  
  
##  <a name="getdocstring"></a>CDocTemplate::GetDocString  
 Ruft eine Zeichenfolge mit dem Dokument verknüpft ist.  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rString`  
 Ein Verweis auf ein `CString` -Objekt, das die Zeichenfolge enthält bei Rückgabe der Funktion.  
  
 *Index*  
 Ein Index der Teilzeichenfolge, die auf die Zeichenfolge, die den Dokumenttyp beschreibt abgerufen werden. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- **CDocTemplate::windowTitle** in das Anwendungsfenster Titelleiste (z. B. "Microsoft Excel") angezeigt. Nur in der Dokumentvorlage für SDI-Anwendung dargestellt.  
  
- **CDocTemplate::docName** Stamm für den Standardnamen des Dokuments (z. B. "Blatt"). Dieses Stammverzeichnis sowie eine Reihe wird für den Standardnamen für ein neues Dokument dieses Typs verwendet, wenn der Benutzer den neuen Befehl im Menü Datei (z. B. "Tabelle1" oder "Tabelle2") auswählt. Wenn nicht angegeben, wird "Unbenannt" als Standardwert verwendet.  
  
- **CDocTemplate:: fileNewName entspricht** Name für diesen Dokumenttyp. Wenn die Anwendung mehr als einen Typ des Dokuments unterstützt, wird diese Zeichenfolge in das Dialogfeld neue Datei (z. B. "Tabelle") angezeigt. Wenn nicht angegeben, ist der Dokumenttyp nicht möglich, über das Menü Datei auf neu.  
  
- **CDocTemplate::filterName** Beschreibung des Dokumenttyps und ein Platzhalterfilter übereinstimmender Dokumente dieses Typs. Diese Zeichenfolge wird in der Liste Dateityp Dropdown-Liste im Dialogfeld Datei öffnen (z. B. "Arbeitsblätter (*.xls)") angezeigt. Wenn nicht angegeben, ist der Dokumenttyp nicht möglich, mit dem Befehl öffnen.  
  
- **CDocTemplate::filterExt** -Erweiterung für Dokumente dieses Typs (z. B. ".xls"). Wenn nicht angegeben, ist der Dokumenttyp nicht möglich, mit dem Befehl öffnen.  
  
- **CDocTemplate::regFileTypeId** Bezeichner für den Dokumenttyp, der in der Registrierungsdatenbank von Windows verwaltet gespeichert werden. Diese Zeichenfolge ist nur zur internen Verwendung (z. B. "ExcelWorksheet"). Wenn nicht angegeben, kann der Dokumenttyp mit dem Windows-Datei-Manager registriert werden.  
  
- **CDocTemplate::regFileTypeName** Name des Dokumenttyps in der Registrierungsdatenbank gespeichert werden. Diese Zeichenfolge kann in den Dialogfeldern der Anwendung angezeigt werden, die Zugriff auf die Registrierungsdatenbank (z. B. "Microsoft Office Excel-Arbeitsblatt).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die angegebene Teilzeichenfolge gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Abrufen einer bestimmten Teilzeichenfolge, die den Dokumenttyp beschreibt. Die Zeichenfolge, die diese Teilzeichenfolgen enthält in die Dokumentvorlage gespeichert und aus einer Zeichenfolge in der Ressourcendatei für die Anwendung abgeleitet ist. Das Framework ruft diese Funktion, um die Zeichenfolgen für die Benutzeroberfläche der Anwendung erforderlichen abzurufen. Wenn Sie die Erweiterung für Dokumente, die die Anwendung angegeben haben, ruft das Framework auch diese Funktion beim Hinzufügen eines Eintrags in der Windows-Registrierungsdatenbank; Dadurch wird der Datei-Manager von Windows Öffnen von Dokumenten.  
  
 Rufen Sie diese Funktion nur, wenn Sie eine eigene Klasse von ableiten `CDocTemplate`.  
  
##  <a name="getfirstdocposition"></a>CDocTemplate::GetFirstDocPosition  
 Ruft die Position des ersten dieser Vorlage zugeordneten Dokuments ab.  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der zum Durchlaufen der Liste dieser Dokumentvorlage; zugeordneten Dokumente verwendet werden kann oder **NULL** , wenn die Liste leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Position des ersten Dokuments in der Liste der Dokumente, die dieser Vorlage zugeordneten abzurufen. Verwenden der **POSITION** Wert als Argument für [CDocTemplate::GetNextDoc](#getnextdoc) zum Durchlaufen der Liste der Dokumente, die der Vorlage zugeordnet.  
  
 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) und [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) überschreiben diese rein virtuelle Funktion. Jede Klasse von ableiten `CDocTemplate` müssen diese Funktion auch überschreiben.  
  
##  <a name="getnextdoc"></a>CDocTemplate::GetNextDoc  
 Ruft das Listenelement identifizierten `rPos`, dann wird `rPos` an der **POSITION** Wert des nächsten Eintrag in der Liste.  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Dokument in der Liste der Dokumente, die mit dieser Vorlage verknüpft sind.  
  
### <a name="parameters"></a>Parameter  
 `rPos`  
 Ein Verweis auf eine **POSITION** von einem vorherigen Aufruf zurückgegebene Wert [GetFirstDocPosition](#getfirstdocposition) oder `GetNextDoc`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das abgerufene Element das letzte Element in der Liste der neue Wert des ist `rPos` Wert **NULL**.  
  
 Sie können `GetNextDoc` in einer Iterationsschleife forward, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten [GetFirstDocPosition](#getfirstdocposition).  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
##  <a name="initialupdateframe"></a>CDocTemplate::InitialUpdateFrame  
 Initialisiert das Rahmenfenster und optional eingeblendet.  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrame`  
 Das Rahmenfenster, das das ursprüngliche Update benötigt wird.  
  
 `pDoc`  
 Das Dokument, das der Frame zugeordnet ist. Kann **NULL**.  
  
 `bMakeVisible`  
 Gibt an, ob der Frame angezeigt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **IntitialUpdateFrame** nach dem Erstellen eines neuen Rahmens mit `CreateNewFrame`. Aufruf dieser Funktion bewirkt, dass die Ansichten in dieser Rahmenfenster erhalten ihre `OnInitialUpdate` aufrufen. Außerdem war es nicht bereits eine aktive Ansicht, wird die Hauptansicht des Rahmenfensters aktiv wird. die primäre Ansicht ist eine Ansicht mit der ID untergeordneten **AFX_IDW_PANE_FIRST**. Schließlich wird das Rahmenfenster sichtbar gemacht Wenn `bMakeVisible` ungleich NULL ist. Wenn `bMakeVisible`&0; (null), die aktueller Fokus und Sichtbarkeitsstatus des Rahmenfensters bleibt unverändert.  
  
 Es ist nicht erforderlich, diese Funktion aufzurufen, wenn die Framework Implementierung von Datei auf neu und öffnen.  
  
##  <a name="loadtemplate"></a>CDocTemplate::LoadTemplate  
 Lädt die Ressourcen für eine bestimmte `CDocTemplate` oder eine abgeleitete Klasse.  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, durch das Framework beim Laden von Ressourcen für eine bestimmte `CDocTemplate` oder eine abgeleitete Klasse. Normalerweise wird sie während der Konstruktion mit Ausnahme aufgerufen, wenn die Vorlage, Global erstellt wird. In diesem Fall wird der Aufruf von `LoadTemplate` verzögert, bis [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) aufgerufen wird.  
  
##  <a name="matchdoctype"></a>CDocTemplate::MatchDocType  
 Bestimmt das Maß an Vertrauen in die Übereinstimmung zwischen einem Dokumenttyp und diese Vorlage.  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Der Pfadname der Datei an, dessen Typ bestimmt werden soll.  
  
 `rpDocMatch`  
 Zeiger auf ein Dokument, das das entsprechende Dokument zugeordnet ist, wenn die von Datei angegebene `lpszPathName` ist bereits geöffnet.  
  
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
 Verwenden Sie diese Funktion, um den Typ der Dokumentvorlage, verwenden Sie zum Öffnen einer Datei zu bestimmen. Wenn Ihre Anwendung mehrere Dateitypen unterstützt, z. B. können diese Funktion zum Ermitteln der verfügbaren Vorlagen für eine bestimmte Datei durch Aufrufen von `MatchDocType` für die einzelnen Vorlagen in und Auswählen einer Vorlage entsprechend dem Wert zurückgegeben.  
  
 Wenn die von Datei angegebene `lpszPathName` ist bereits geöffnet ist, gibt diese Funktion **CDocTemplate::yesAlreadyOpen** und kopiert die Datei **CDocument** Objekt in das Objekt am `rpDocMatch`.  
  
 Ist die Datei nicht geöffnet ist, aber die Erweiterung in `lpszPathName` mit der angegebenen Erweiterung übereinstimmt **CDocTemplate::filterExt**, gibt diese Funktion **CDocTemplate::yesAttemptNative** und `rpDocMatch` auf **NULL**. Weitere Informationen zu **CDocTemplate::filterExt**, finden Sie unter [CDocTemplate::GetDocString](#getdocstring).  
  
 Wenn keinem Fall auf true festgelegt ist, gibt die Funktion **CDocTemplate::yesAttemptForeign**.  
  
 Die standardmäßige Implementierung kehrt **CDocTemplate::maybeAttemptForeign** oder **CDocTemplate::maybeAttemptNative**. Überschreiben Sie diese Funktion zum Implementieren der übereinstimmende Typ Logik aus Ihrer Anwendung, z. B. mit diesen beiden Werten aus der **vertrauen** Enumeration.  
  
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
 Zeiger auf den Pfad der Datei, die dem Dokument geöffnet werden.  
  
 [in] `bAddToMRU`  
 `TRUE`Gibt an, dass das Dokument ist eine der neuesten Dateien. `FALSE` gibt an, das Dokument ist nicht die aktuellsten Dateien.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, dessen Datei mit den Namen von `lpszPathName`; `NULL` gelingt.  
  
### <a name="remarks"></a>Hinweise  
 Öffnet die Datei, deren Pfad, indem angegeben wird `lpszPathName`. Wenn `lpszPathName` ist `NULL`, eine neue Datei, die ein Dokument vom Typ dieser Vorlage zugeordneten enthält erstellt wird.  
  
##  <a name="removedocument"></a>CDocTemplate::RemoveDocument  
 Hiermit wird das Dokument auf den `pDoc` aus der Liste der Dokumente, die mit dieser Vorlage verknüpft sind.  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Ein Zeiger auf das Dokument entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die abgeleiteten Klassen `CMultiDocTemplate` und `CSingleDocTemplate` überschreiben. Wenn Sie eine eigene Klasse Dokumentvorlagen von ableiten `CDocTemplate`, die abgeleitete Klasse muss diese Funktion überschreibt.  
  
##  <a name="saveallmodified"></a>CDocTemplate::SaveAllModified  
 Speichert alle Dokumente, die geändert wurden.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich; andernfalls 0.  
  
##  <a name="setcontainerinfo"></a>CDocTemplate::SetContainerInfo  
 Bestimmt, welche Ressourcen für die OLE-Container bei einem direkten OLE-Element zu bearbeiten.  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDOleInPlaceContainer`  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt aktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Festlegen der Ressourcen verwendet werden, wenn ein OLE-Objekt aktiviert ist. Diese Ressourcen können Menüs und Zugriffstastentabellen enthalten. Diese Funktion wird in der Regel aufgerufen, der [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Funktion Ihrer Anwendung.  
  
 Klicken Sie im Menü zugeordneten `nIDOleInPlaceContainer` Trennzeichen, die im Menü des aktivierten direktes Elements Zusammenführen mit dem Menü von der Container-Anwendung zu ermöglichen. Weitere Informationen zum Zusammenführen von Menüs für Server und-Container finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="setdefaulttitle"></a>CDocTemplate::SetDefaultTitle  
 Rufen Sie diese Funktion, um den Titel des Dokuments standardmäßig geladen und in der Titelleiste des Dokuments angezeigt wird.  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *pDocument*  
 Ein Zeiger auf das Dokument, dessen Titel festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu den Standardtitel, finden Sie unter der Beschreibung der **CDocTemplate::docName** in [CDocTemplate::GetDocString](#getdocstring).  
  
##  <a name="setserverinfo"></a>CDocTemplate::SetServerInfo  
 Wenn das Serverdokument eingebettet oder direktes bearbeitet die Ressourcen und Klassen bestimmt werden soll.  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDOleEmbedding*  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt in einem separaten Fenster geöffnet wird.  
  
 `nIDOleInPlaceServer`  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt aktiviert an.  
  
 *pOleFrameClass*  
 Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur, die Klasseninformationen für die Frame-Window-Objekt erstellt, wenn die direkte Aktivierung enthält.  
  
 *pOleViewClass*  
 Zeiger auf eine `CRuntimeClass` -Struktur, die Klasseninformationen für das View-Objekt erstellt, wenn die direkte Aktivierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Identifizieren von Ressourcen, die von der Serveranwendung verwendet wird, wenn der Benutzer die Aktivierung eines eingebetteten Objekts anfordert. Diese Ressourcen umfassen Menüs und Zugriffstastentabellen. Diese Funktion wird in der Regel aufgerufen, der `InitInstance` der Anwendung.  
  
 Klicken Sie im Menü zugeordneten `nIDOleInPlaceServer` Trennzeichen, mit denen im Menü "Server" zum Zusammenführen mit dem Menü des Containers enthält. Weitere Informationen zum Zusammenführen von Menüs für Server und-Container finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="createpreviewframe"></a>CDocTemplate::CreatePreviewFrame  
 Erstellt einen untergeordneten Frame for Rich Preview verwendet.  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf ein übergeordnetes Fenster (in der Regel von der Shell bereitgestellt).  
  
 `pDoc`  
 Ein Zeiger auf ein Document-Objekt, dessen Inhalt in der Vorschau angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf eine `CFrameWnd` -Objekt, oder `NULL` Wenn die Erstellung fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpreviewinfo"></a>CDocTemplate::SetPreviewInfo  
 Legt fest, die außerhalb der Vorschauhandler Prozess.  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDPreviewFrame`  
 Gibt eine Ressourcen-ID im Vorschau-Fenster.  
  
 `pPreviewFrameClass`  
 Gibt einen Zeiger auf eine Struktur Common Language Runtime-Klasse im Vorschau-Fenster.  
  
 `pPreviewViewClass`  
 Gibt einen Zeiger auf eine Struktur Common Language Runtime-Klasse der Vorschauansicht.  
  
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

