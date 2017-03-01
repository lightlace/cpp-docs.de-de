---
title: Klasse CDataRecoveryHandler | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataRecoveryHandler
dev_langs:
- C++
helpviewer_keywords:
- CDataRecoveryHandler class
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
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
ms.openlocfilehash: c2a99e32a88b8cb3f12d0961451025596886abb0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler-Klasse
Die `CDataRecoveryHandler` speichert Dokumente automatisch und stellt sie wieder her, wenn eine Anwendung unerwartet beendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Erstellt ein `CDataRecoveryHandler`-Objekt.|  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Speichert jede Datei registriert die `CDataRecoveryHandler` Klasse.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Speichert das angegebene Dokument.|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Die Liste der geöffneten Dokumente hinzugefügt ein Dokument.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Löscht die aktuellen automatisch gespeicherte Dateien.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Löscht die angegebene automatisch gespeicherte Datei.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Generiert den Namen für eine Sicherungsdatei mit dem angegebenen Dateinamen verknüpft ist.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Gibt das Intervall zwischen Autosave versucht zurück.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Gibt den Pfad der Dateien automatisch gespeichert.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Ruft den Namen des Dokuments aus einem `CDocument` Objekt.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Ruft den normalen Titel für das angegebene Dokument ab.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Erstellt und gibt den Titel für das wiederhergestellte Dokument.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Ruft den eindeutigen Neustart für die Anwendung.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Gibt an, ob die `CDataRecoveryHandler` führt eine automatische Speicherung auf der aktuellen Leerlaufschleife.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Gibt an, ob der Neustart-Manager die zum Beenden der Anwendung verursacht.|  
|[CDataRecoveryHandler::Initialize](#initialize)|Initialisiert das `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Zeigt ein Dialogfeld für den Benutzer an, für jedes Dokument, das die `CDataRecoveryHandler` automatisch gespeichert. Das Dialogfeld bestimmt, ob der Benutzer das Dokument automatisch wiederherstellen möchte.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Lädt die Liste der geöffneten Dokument aus der Registrierung.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Entfernt das angegebene Dokument aus der Liste der geöffneten Dokument.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Öffnet die vorher geöffnete Dokumente.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Stellt die automatisch gespeicherte Dokumente auf Grundlage der Benutzereingabe.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Die aktuelle Liste der geöffneten Dokumente in der Windows-Registrierung gespeichert.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Legt die Zeit zwischen Autosave Zyklen in Millisekunden fest.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Legt fest, dass das Verzeichnis, in dem Dateien automatisch gespeichert werden.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Den Neustart des eindeutigen Bezeichner für diese Instanz von legt die `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Legt fest, ob die `CDataRecoveryHandler` speichert die geöffnete Dokument-Informationen zur Windows-Registrierung während des Zyklus der aktuelle im Leerlauf.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Legt fest, ob es sich bei der vorherige Beenden der Anwendung durch den Neustart-Manager verursacht wurde.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Die Informationen für ein Dokument aktualisiert, da der Benutzer dieses gespeichert.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|Gibt an, ob Daten Recovery-Handler vorher geöffnete Dokumente erneut geöffnet.|  
|m_bSaveDocumentInfoOnIdle|Gibt an, ob die Daten Wiederherstellung Handler speichert auf der nächsten Leerlaufschleife dokumentiert.|  
|m_bShutdownByRestartManager|Gibt an, ob der Neustart-Manager bewirkt, die Anwendung dass zu beenden.|  
|m_dwRestartManagerSupportFlags|Flags, die angeben, welche den Neustart-Manager unterstützt bietet für die Anwendung.|  
|m_lstAutosavesToDelete|Eine Liste der Dateien automatisch gespeichert, die nicht gelöscht wurden, wenn die ursprünglichen Dokumente geschlossen wurden. Wenn die Anwendung, die Neustart-Manager Wiederholungen Löschen der Dateien beendet wird.|  
|m_mapDocNameToAutosaveName|Eine Karte mit den Dokumentnamen, die Dateinamen automatisch gespeichert.|  
|m_mapDocNameToDocumentPtr|Eine Übersicht über die Dokumentnamen der [CDocument](../../mfc/reference/cdocument-class.md) Zeiger.|  
|m_mapDocNameToRestoreBool|Eine Übersicht über die Dokumentnamen ein boolescher Parameter, der angibt, ob das Dokument automatisch wiederhergestellt werden.|  
|m_mapDocumentPtrToDocName|Eine Übersicht der `CDocument` Zeiger auf den Dokumentnamen.|  
|m_mapDocumentPtrToDocTitle|Eine Übersicht der `CDocument` Zeiger auf die Dokumenttitel. Diese Titel werden zum Speichern von Dateien verwendet.|  
|m_nAutosaveInterval|Die Zeit in Millisekunden zwischen speichert.|  
|m_nTimerID|Der Bezeichner für den Zeitgeber für die automatische Speicherung.|  
|m_strAutosavePath|Der Speicherort, wo die automatisch gespeicherte Dokumente gespeichert werden.|  
|m_strRestartIdentifier|Die Zeichenfolgendarstellung einer GUID für den Neustart-Manager.|  
  
## <a name="remarks"></a>Hinweise  
 Der Neustart-Manager verwendet die `CDataRecoveryHandler` Klasse zu verfolgen aller geöffneten Dokumente und AutoSpeichern nach Bedarf. Um die automatische Speicherung zu aktivieren, verwenden die [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) Methode. Diese Methode leitet den `CDataRecoveryHandler` eine automatische Speicherung auf der nächsten Leerlaufschleife ausführen. Der Neustart-Manager ruft `SetSaveDocumentInfoOnIdle` bei der `CDataRecoveryHandler` sollten eine automatische Speicherung durchführen.  
  
 Alle Methoden von der `CDataRecoveryHandler` Klasse virtuell sind. Überschreiben Sie die Methoden in dieser Klasse, um Ihren eigenen benutzerdefinierten Daten Recovery-Handler zu erstellen. Es sei denn, Sie Ihre eigenen Daten Recovery-Handler erstellen oder-Manager Neustart, instanziieren Sie ein CDataRecoveryHandler nicht. Die [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md) erstellt ein `CDataRecoveryHandler` Objekt, wie dies erforderlich ist.  
  
 Vor der Verwendung einer `CDataRecoveryHandler` -Objekt, Sie müssen [CDataRecoveryHandler::Initialize](#initialize).  
  
 Da die `CDataRecoveryHandler` ist eng mit den Neustart-Manager verbunden `CDataRecoveryHandler` hängt von der globalen Parameter `m_dwRestartManagerSupportFlags`. Dieser Parameter bestimmt, welche Berechtigungen der Neustart-Manager hat und der Interaktion mit der Anwendung. Um den Neustart-Manager in eine vorhandene Anwendung integrieren, müssen Sie weisen `m_dwRestartManagerSupportFlags` den entsprechenden Wert im Konstruktor der Hauptassembly der Anwendung. Weitere Informationen dazu, wie Sie den Neustart-Manager verwenden, finden Sie unter [How to: Add Restart Manager Support](../../mfc/how-to-add-restart-manager-support.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdatarecovery.h  
  
##  <a name="a-nameautosavealldocumentinfoa--cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo  
 Speichert jede Datei registriert die `CDataRecoveryHandler` Klasse.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `CDataRecoveryHandler` speichern alle Dokumente; `FALSE` , wenn ein Dokument nicht gespeichert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `TRUE` befinden sich keine Dokumente, die gespeichert werden müssen. Es gibt auch `TRUE` ohne Dokumente speichern, wenn das Abrufen der `CWinApp` oder `CDocManager` für die Anwendung einen Fehler generiert.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` oder `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` muss festgelegt werden, `m_dwRestartManagerSupportFlags`. Finden Sie unter [M_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) Weitere Informationen.  
  
##  <a name="a-nameautosavedocumentinfoa--cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo  
 Speichert das angegebene Dokument.  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf die `CDocument` zu speichern.|  
|[in] `bResetModifiedFlag`|`TRUE`Gibt an, dass die `CDataRecoveryHandler` berücksichtigt `pDocument` geändert werden; `FALSE` gibt an, dass das Framework berücksichtigt `pDocument` nicht geändert werden. Finden Sie im Abschnitt "Hinweise" für Weitere Informationen zu den Auswirkungen dieses Flags.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die entsprechenden Flags festgelegt sind und `pDocument` ist ein gültiger `CDocument` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Jedes `CDocument` Objekt verfügt über ein Flag, das angibt, ob es seit der letzten Speicherung geändert wurde. Verwendung [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) , den Status dieses Flags zu bestimmen. Wenn ein `CDocument` wurde seit dem letzten Speichern, `AutosaveDocumentInfo` löscht automatisch gespeicherte Dateien für dieses Dokument. Wenn ein Dokument seit der letzten Speicherung geändert wurde, schließen die Benutzer aufgefordert, das Dokument vor dem Schließen gespeichert.  
  
> [!NOTE]
>  Mithilfe von `bResetModifiedFlag` , den Status des Dokuments auf unmodified ändern können, dass der Benutzer nicht gespeicherte Daten verloren gehen. Das Framework ein Dokument unverändert hält, wird das Schließen nicht den Benutzer zum Speichern aufgefordert.  
  
 Diese Methode löst eine Ausnahme mit der [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) Makro Wenn `pDocument` ist kein gültiger `CDocument` Objekt.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` oder `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
##  <a name="a-namecdatarecoveryhandlera--cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler  
 Erstellt ein `CDataRecoveryHandler`-Objekt.  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `dwRestartManagerSupportFlags`|Gibt an, welche Optionen für den Neustart-Manager unterstützt werden.|  
|[in] `nAutosaveInterval`|Die Zeit zwischen speichert. Dieser Parameter wird in Millisekunden angegeben.|  
  
### <a name="remarks"></a>Hinweise  
 Das MFC-Framework erstellt automatisch eine `CDataRecoveryHandler` -Objekt für die Anwendung bei Verwendung der **neues Projekt** Assistenten. Wenn Sie das Wiederherstellungsverhalten Daten oder der Neustart-Manager anpassen, erstellen Sie keine `CDataRecoveryHandler` Objekt.  
  
  
##  <a name="a-namecreatedocumentinfoa--cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 Die Liste der geöffneten Dokumente hinzugefügt ein Dokument.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf eine `CDocument`. Diese Methode erstellt die Dokumentinformationen für diesen `CDocument`.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft, ob `pDocument` ist bereits in der Liste der Dokumente, bevor das Dokument hinzugefügt. Wenn `pDocument` bereits in der Liste ist, diese Methode löscht die Datei automatisch zugeordnet `pDocument`.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` oder `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` muss festgelegt werden, `m_dwRestartManagerSupportFlags`. 
  
##  <a name="a-namedeleteallautosavedfilesa--cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles  
 Löscht die aktuellen automatisch gespeicherte Dateien.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung gibt immer `TRUE`.  
  
##  <a name="a-namedeleteautosavedfilea--cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile  
 Löscht die angegebene automatisch gespeicherte Datei.  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `strAutosavedFile`|Eine Zeichenfolge, die Namen der automatisch gespeicherte Datei enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung immer return `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode die Datei automatisch gelöscht werden kann, wird der Name der Datei in einer Liste gespeichert. Der Destruktor für die `CDataRecoveryHandler` versucht, jede automatisch gespeicherte Datei angegeben, die in der Liste zu löschen.  
  
##  <a name="a-namegenerateautosavefilenamea--cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 Generiert den Namen für eine Sicherungsdatei mit dem angegebenen Dateinamen verknüpft ist.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strDocumentName`  
 Eine Zeichenfolge, die den Namen des Dokuments enthält. `GenerateAutosaveFileName`verwendet diese Dokument zum Generieren eines entsprechenden Autosave-Datei namens.  
  
### <a name="return-value"></a>Rückgabewert  
 Der von generierte Autosave-Dateiname `strDocumentName`.  
  
### <a name="remarks"></a>Hinweise  
 Jedes der Dokumentname hat eine Zuordnung mit einem Dateinamen autosave  
  
##  <a name="a-namegetautosaveintervala--cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 Gibt das Intervall zwischen Autosave versucht zurück.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Millisekunden zwischen Autosave versucht.  
  
##  <a name="a-namegetautosavepatha--cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 Gibt den Pfad der Dateien automatisch gespeichert.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Speicherort, wo die automatisch gespeicherte Dokumente gespeichert werden.  
  
##  <a name="a-namegetdocumentlistnamea--cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 Ruft den Namen des Dokuments aus einem `CDocument` Objekt.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf eine `CDocument`. `GetDocumentListName`Ruft den Namen des Dokuments aus diesem `CDocument`.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Dokumentname aus `pDocument`.  
  
### <a name="remarks"></a>Hinweise  
 Die `CDataRecoveryHandler` verwendet den Namen des Dokuments als Schlüssel in `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, und `m_mapDocNameToRestoreBool`. Aktivieren Sie diese Parameter der `CDataRecoveryHandler` Überwachen `CDocument` Objekte, die Autosave-Dateinamen und die Einstellungen für die automatische Speicherung.  
  
##  <a name="a-namegetnormaldocumenttitlea--cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
 Ruft den normalen Titel für das angegebene Dokument ab.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf eine `CDocument`.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der normale Titel für das angegebene Dokument.  
  
### <a name="remarks"></a>Hinweise  
 Die normalen Titel eines Dokuments wird in der Regel den Dateinamen des Dokuments ohne Pfad. Dies ist der Titel in der **Dateinamen** Feld der **speichern** Dialogfeld.  
  
##  <a name="a-namegetrecovereddocumenttitlea--cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 Erstellt und gibt den Titel für das wiederhergestellte Dokument.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strDocumentTitle`  
 Der normale Titel für das Dokument.  
  
### <a name="return-value"></a>Rückgabewert  
 Der wiederhergestellte Dokument-Titel.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist der wiederhergestellten Titel eines Dokuments den normalen Titel **[wiederhergestellt]** angefügt ist. Der wiederhergestellten Titel wird angezeigt, die dem Benutzer bei der `CDataRecoveryHandler` fragt den Benutzer automatisch gespeicherte Dokumente wiederherstellen.  
  
##  <a name="a-namegetrestartidentifiera--cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 Ruft den eindeutigen Neustart für die Anwendung.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bezeichner der eindeutigen neu starten.  
  
### <a name="remarks"></a>Hinweise  
 Der Neustart-Bezeichner ist eindeutig für jede Ausführung der Anwendung.  
  
 Der `CDataRecoveryHandler` speichert Informationen in der Registrierung über die derzeit geöffneten Dokumente. Wenn der Neustart-Manager eine Anwendung beendet und startet ihn neu, stellt den Neustart-Bezeichner, der die `CDataRecoveryHandler`. Die `CDataRecoveryHandler` verwendet die Neustart-ID zum Abrufen der Liste der zuvor geöffneten Dokumente. Auf diese Weise können die `CDataRecoveryHandler` , zu suchen und automatisch gespeicherte Dateien wiederherstellen.  
  
##  <a name="a-namegetsavedocumentinfoonidlea--cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 Gibt an, ob die `CDataRecoveryHandler` führt eine automatische Speicherung auf der aktuellen Leerlaufschleife.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt die `CDataRecoveryHandler` automatisch auf der aktuellen Leerlaufschleife; `FALSE` gibt es nicht.  
  
##  <a name="a-namegetshutdownbyrestartmanagera--cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 Gibt an, ob der Neustart-Manager die zum Beenden der Anwendung verursacht.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass der Neustart-Manager die Anwendung beendet hat. `FALSE` gibt es nicht.  
  
##  <a name="a-nameinitializea--cdatarecoveryhandlerinitialize"></a><a name="initialize"></a>CDataRecoveryHandler::Initialize  
 Initialisiert das `CDataRecoveryHandler`.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Initialisierung erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Initialisierung wird der Pfad zum Speichern der Autosave-Dateien aus der Registrierung geladen. Wenn die `Initialize` Methode kann nicht gefunden oder der Pfad ist `NULL`, `Initialize` schlägt fehl und gibt `FALSE`.  
  
 Verwendung [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) AutoSpeichern-Pfad zu ändern, nachdem die Anwendung initialisiert das `CDataRecoveryHandler`.  
  
 Die `Initialize` Methode startet einen Zeitgeber zu überwachen, wenn die nächste Autosave auftritt. Verwendung [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) das Intervall für die automatische Speicherung zu ändern, nachdem die Anwendung initialisiert das `CDataRecoveryHandler`.  
  
##  <a name="a-namequeryrestoreautosaveddocumentsa--cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 Zeigt ein Dialogfeld für den Benutzer an, für jedes Dokument, das die `CDataRecoveryHandler` automatisch gespeichert. Das Dialogfeld bestimmt, ob der Benutzer das Dokument automatisch wiederherstellen möchte.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung Unicode ist, zeigt diese Methode ein [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) für den Benutzer. Andernfalls verwendet das Framework [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) um vom Benutzer abzufragen.  
  
 Nach dem `QueryRestoreAutosavedDocuments` sammelt alle Antworten des Benutzers, speichert er die Informationen in der Membervariablen `m_mapDocNameToRestoreBool`. Diese Methode wird die automatisch gespeicherte Dokumente nicht wiederhergestellt.  
  
##  <a name="a-namereadopendocumentlista--cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 Lädt die Liste der geöffneten Dokument aus der Registrierung.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass `ReadOpenDocumentList` die Informationen für mindestens ein Dokument aus der Registrierung geladen `FALSE` gibt an, keine Informationen im Dokument geladen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion lädt die geöffneten Dokumentinformationen aus der Registrierung und speichert ihn in der Membervariablen `m_mapDocNameToAutosaveName`.  
  
 Nach dem `ReadOpenDocumentList` lädt alle Daten, die Informationen aus der Registrierung gelöscht.  
  
##  <a name="a-nameremovedocumentinfoa--cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo  
 Entfernt das angegebene Dokument aus der Liste der geöffneten Dokument.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf das Dokument zu entfernen.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pDocument` entfernt wurde, aus der Liste. `FALSE` , wenn ein Fehler aufgetreten ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer ein Dokument geschlossen wird, verwendet das Framework diese Methode von der Liste der geöffneten Dokumente entfernen.  
  
 Wenn `RemoveDocumentInfo` kann nicht gefunden werden `pDocument` in der Liste der geöffneten Dokumente, es wird keine Aktion ausgeführt, und gibt `TRUE`.  
  
 Mithilfe dieser Methode `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
##  <a name="a-namereopenpreviousdocumentsa--cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 Öffnet die vorher geöffnete Dokumente.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn mindestens ein Dokument geöffnet wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode öffnet die letzten Speichern der zuvor geöffneten Dokumente. Wenn ein Dokument nicht gespeichert wurde, oder automatisch, `ReopenPreviousDocuments` öffnet ein leeres Dokument basierend auf der Vorlage für diesen Dateityp.  
  
 Mithilfe dieser Methode `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`. Wenn dieser Parameter nicht festgelegt ist, `ReopenPreviousDocuments` gibt `FALSE`.  
  
 Wenn keine in der Liste der zuvor geöffneten Dokumente gespeichert Dokumente `ReopenPreviousDocuments` gibt `FALSE`.  
  
##  <a name="a-namerestoreautosaveddocumentsa--cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 Stellt die automatisch gespeicherte Dokumente auf Grundlage der Benutzereingabe.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn es sich bei dieser Methode werden die Dokumente erfolgreich wiederhergestellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) um zu bestimmen, die den Benutzer Dokumente wiederherstellen möchte. Wenn ein Benutzer kein Dokument automatisch wiederherstellen `RestoreAutosavedDocuments` löscht der Sicherungsdatei. Andernfalls `RestoreAutosavedDocuments` das geöffnete Dokument durch die automatisch gespeicherte Version ersetzt.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` oder `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
##  <a name="a-namesaveopendocumentlista--cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 Die aktuelle Liste der geöffneten Dokumente in der Windows-Registrierung gespeichert.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn es keine geöffneten Dokumente sind speichern, oder wenn sie erfolgreich gespeichert wurden. `FALSE`Wenn Dokumente in der Registrierung gespeichert sind, aber sie nicht gespeichert wurden, da ein Fehler aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Der Neustart-Manager ruft `SaveOpenDocumentList` Wenn die Anwendung unerwartet beendet wird oder wenn er für eine Aktualisierung beendet wird. Wenn die Anwendung neu gestartet wird, verwendet es [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) zum Abrufen der Liste der geöffneten Dokumente.  
  
 Diese Methode speichert nur die Liste der geöffneten Dokumente. Die Methode [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) ist zum Speichern der Dokumente selbst verantwortlich.  
  
##  <a name="a-namesetautosaveintervala--cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 Legt die Zeit zwischen Autosave Zyklen in Millisekunden fest.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nAutosaveInterval`  
 Das neue Autosave-Intervall in Millisekunden.  
  
##  <a name="a-namesetautosavepatha--cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 Legt fest, dass das Verzeichnis, in dem Dateien automatisch gespeichert werden.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `strAutosavePath`|Der Pfad, in dem Autosave-Dateien gespeichert sind.|  
  
### <a name="remarks"></a>Hinweise  
 Ändern der AutoSpeichern-Verzeichnis verschoben nicht aktuell automatisch gespeicherte Dateien.  
  
##  <a name="a-namesetrestartidentifiera--cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 Den Neustart des eindeutigen Bezeichner für diese Instanz von legt die `CDataRecoveryHandler`.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `strRestartIdentifier`|Der eindeutige Bezeichner für den Neustart-Manager.|  
  
### <a name="remarks"></a>Hinweise  
 Der Neustart-Manager zeichnet Informationen über die offenen Dokumente in der Registrierung. Diese Informationen werden mit dem Neustart des eindeutigen Bezeichner als Schlüssel gespeichert. Da die Neustart-Bezeichner für jede Instanz einer Anwendung eindeutig ist, mehrere Instanzen einer Anwendung möglicherweise unerwartet beendet und der Neustart-Manager kann diese wiederhergestellt werden.  
  
##  <a name="a-namesetsavedocumentinfoonidlea--cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 Legt fest, ob die `CDataRecoveryHandler` speichert die geöffnete Dokument-Informationen zur Windows-Registrierung während des Zyklus der aktuelle im Leerlauf.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `bSaveOnIdle`|`TRUE`Um Dokumentinformationen während des Zyklus der aktuelle im Leerlauf zu speichern. `FALSE to not perform a save`.|  
  
##  <a name="a-namesetshutdownbyrestartmanagera--cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 Legt fest, ob es sich bei der vorherige Beenden der Anwendung durch den Neustart-Manager verursacht wurde.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `bShutdownByRestartManager`|`TRUE`um anzugeben, dass der Neustart-Manager die zum Beenden der Anwendung verursacht. `FALSE` an, dass die Anwendung aus einem anderen Grund beendet.|  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verhält sich anders basierend auf, ob das vorherige verlassen wurde oder ob er durch den Neustart-Manager initiiert wurde.  
  
##  <a name="a-nameupdatedocumentinfoa--cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
 Die Informationen für ein Dokument aktualisiert, da der Benutzer dieses gespeichert.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf das gespeicherte Dokument.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode das Dokument automatisch gelöscht und die Dokumentinformationen aktualisiert; `FALSE` , wenn ein Fehler aufgetreten ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer ein Dokument speichert, entfernt die Anwendung die Datei automatisch, da sie nicht mehr benötigt wird. `UpdateDocumentInfo`Löscht die Datei automatisch durch Aufrufen von [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo`fügt dann die Informationen aus `pDocument` der Liste der derzeit öffnen Dokumente da `RemoveDocumentInfo` löscht diese Informationen, sondern die gespeicherte Dokument noch geöffnet ist.  
  
 Mithilfe dieser Methode `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Gewusst wie: Hinzufügen von Unterstützung für Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md)


