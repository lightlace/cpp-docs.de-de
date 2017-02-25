---
title: "CDataRecoveryHandler Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataRecoveryHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataRecoveryHandler class"
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CDataRecoveryHandler Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDataRecoveryHandler` speichert Dokumente automatisch und stellt sie beim Verlassen einer Anwendung unerwartet wieder her.  
  
## Syntax  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](../Topic/CDataRecoveryHandler::CDataRecoveryHandler.md)|Erstellt ein `CDataRecoveryHandler`\-Objekt.|  
  
### Methoden  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveAllDocumentInfo.md)|Speichert jede Datei automatisch, die mit der `CDataRecoveryHandler`\-Klasse registriert wird.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveDocumentInfo.md)|Speichert das angegebene Dokument automatisch.|  
|[CDataRecoveryHandler::CreateDocumentInfo](../Topic/CDataRecoveryHandler::CreateDocumentInfo.md)|Fügt ein Dokument der Liste der geöffneten Dokumenten hinzu.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](../Topic/CDataRecoveryHandler::DeleteAllAutosavedFiles.md)|Löscht alle aktuellen automatisch gespeicherten Dateien.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](../Topic/CDataRecoveryHandler::DeleteAutosavedFile.md)|Löscht die angegebene automatisch gespeicherte Datei.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](../Topic/CDataRecoveryHandler::GenerateAutosaveFileName.md)|Generiert den Namen für eine Automatisch speichung Datei, die mit dem angegebenen Dokumentendateinamen zugeordnet ist.|  
|[CDataRecoveryHandler::GetAutosaveInterval](../Topic/CDataRecoveryHandler::GetAutosaveInterval.md)|Gibt das Intervall zwischen automatisch speichern Versuche zurück.|  
|[CDataRecoveryHandler::GetAutosavePath](../Topic/CDataRecoveryHandler::GetAutosavePath.md)|Gibt den Pfad der automatisch gespeicherten Dateien zurück.|  
|[CDataRecoveryHandler::GetDocumentListName](../Topic/CDataRecoveryHandler::GetDocumentListName.md)|Ruft den Dokumentnamen von einem `CDocument`\-Objekt ab.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](../Topic/CDataRecoveryHandler::GetNormalDocumentTitle.md)|Ruft den normalen Namen für das angegebene Dokument ab.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](../Topic/CDataRecoveryHandler::GetRecoveredDocumentTitle.md)|Erstellt und gibt den Namen für das wiederhergestellte Dokument zurück.|  
|[CDataRecoveryHandler::GetRestartIdentifier](../Topic/CDataRecoveryHandler::GetRestartIdentifier.md)|Ruft den eindeutigen Neustartbezeichner für die Anwendung ab.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle.md)|Gibt an, ob ein `CDataRecoveryHandler` Automatisch speichung auf der aktuellen Leerlaufschleife ausführt.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](../Topic/CDataRecoveryHandler::GetShutdownByRestartManager.md)|Gibt an, ob die Anwendung vom Neustart\-Manager verursacht hat zu beenden.|  
|[CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md)|Initialisiert `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::QueryRestoreAutosavedDocuments.md)|Zeigt ein Dialogfeld an den Benutzer für jedes Dokument, das `CDataRecoveryHandler` automatisch gespeichert ist.  Das Dialogfeld bestimmt, ob der Benutzer automatisch das gespeicherte Dokument wiederherstellen möchte.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](../Topic/CDataRecoveryHandler::ReadOpenDocumentList.md)|Lädt die Liste des geöffneten Dokuments aus der Registrierung.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](../Topic/CDataRecoveryHandler::RemoveDocumentInfo.md)|Entfernt das angegebene Dokument aus der Liste der geöffneten Dokuments.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](../Topic/CDataRecoveryHandler::ReopenPreviousDocuments.md)|Öffnet die zuvor geöffneten Dokumente.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::RestoreAutosavedDocuments.md)|Stellt die automatisch gespeicherten Dokumente auf Grundlage der Benutzereingabe wieder her.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](../Topic/CDataRecoveryHandler::SaveOpenDocumentList.md)|Speichert die aktuelle Liste der geöffneten Dokumenten zur Windows\-Registrierung.|  
|[CDataRecoveryHandler::SetAutosaveInterval](../Topic/CDataRecoveryHandler::SetAutosaveInterval.md)|Legt die Zeit zwischen automatisch speichern Zyklen in Millisekunden fest.|  
|[CDataRecoveryHandler::SetAutosavePath](../Topic/CDataRecoveryHandler::SetAutosavePath.md)|Legt das Verzeichnis fest, in dem automatisch gespeicherte Dateien gespeichert sind.|  
|[CDataRecoveryHandler::SetRestartIdentifier](../Topic/CDataRecoveryHandler::SetRestartIdentifier.md)|Legt den eindeutigen Neustartbezeichner für diese Instanz `CDataRecoveryHandler` fest.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md)|Legt fest, ob `CDataRecoveryHandler` die Informationen des geöffneten Dokuments der Windows\-Registrierung während des aktuellen Schleife im Leerlauf gespeichert werden.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](../Topic/CDataRecoveryHandler::SetShutdownByRestartManager.md)|Legt fest, ob die vorherige zum Beenden der Anwendung vom Neustart\-Manager verursacht wurde.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](../Topic/CDataRecoveryHandler::UpdateDocumentInfo.md)|Aktualisiert die Informationen für ein Dokument, da der Benutzer es gespeichert ist.|  
  
### Datenmember  
  
|||  
|-|-|  
|m\_bRestoringPreviousOpenDocs|Gibt an, ob der Datenwiederherstellungshandler zuvor geöffnete Dokumente erneut öffnet.|  
|m\_bSaveDocumentInfoOnIdle|Gibt an, ob der Datenwiederherstellungshandler Dokumente auf der folgenden Leerlaufschleife automatisch speichert.|  
|m\_bShutdownByRestartManager|Gibt an, ob die Anwendung vom Neustart\-Manager verursacht zu beenden.|  
|m\_dwRestartManagerSupportFlags|Flags, die angeben, welche Unterstützung der Neustart\-Manager für die Anwendungen bietet.|  
|m\_lstAutosavesToDelete|Eine Liste von automatisch gespeicherten Dateien, die nicht gelöscht wurden, als die Originaldokumente geschlossen.  Wenn die wegen der Neustart\-Manager, das Löschen der Dateien erneut versucht.|  
|m\_mapDocNameToAutosaveName|Eine Zuordnung der Dokumentnamen zu den automatisch gespeicherten Dateinamen.|  
|m\_mapDocNameToDocumentPtr|Eine Zuordnung der Dokumentnamen zu den [CDocument](../../mfc/reference/cdocument-class.md) Zeiger.|  
|m\_mapDocNameToRestoreBool|Eine Zuordnung der Dokumentnamen als booleschen Parameter, der angibt, ob das gespeicherte Dokument automatisch hinzugefügt.|  
|m\_mapDocumentPtrToDocName|Eine Zuordnung der `CDocument` Zeiger auf den Dokumentnamen.|  
|m\_mapDocumentPtrToDocTitle|Eine Zuordnung der `CDocument` Zeiger auf Dokumentennamen.  Diese Namen werden zum Speichern von Dateien verwendet.|  
|m\_nAutosaveInterval|Zeit in Millisekunden zwischen speichert automatisch.|  
|m\_nTimerID|Der Bezeichner für den Automatisch speichung Zeitgeber.|  
|m\_strAutosavePath|Der Speicherort, an dem die automatisch gespeicherten Dokumente gespeichert werden.|  
|m\_strRestartIdentifier|Die Zeichenfolgendarstellung eines GUID für den Neustart\-Manager.|  
  
## Hinweise  
 Der Neustart\-Manager verwendet die `CDataRecoveryHandler`\-Klasse, um alle geöffneten Dokumente zu verfolgen und bei Bedarf automatisch zu speichern.  So aktivieren Sie automatisch speichern, verwenden Sie die Methode [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md).  Diese Methode verweist `CDataRecoveryHandler`, ein Automatisch speichung auf der folgenden Leerlaufschleife auszuführen.  Der Neustart\-Manager `SetSaveDocumentInfoOnIdle` ruft auf, wenn ein `CDataRecoveryHandler` Automatisch speichung ausführen soll.  
  
 Alle Methoden der Klasse `CDataRecoveryHandler` sind virtuell.  Überschreiben Sie die Methoden dieser Klasse, einen eigenen benutzerdefinierten Datenwiederherstellungshandler zu erstellen.  Es sei denn, Sie eigenen Datenwiederherstellungshandler erstellen oder Manager neu starten, instanziieren Sie kein CDataRecoveryHandler.  [CWinApp Class](../../mfc/reference/cwinapp-class.md) erstellt ein Objekt `CDataRecoveryHandler`, während es erforderlich ist.  
  
 Bevor Sie ein Objekt `CDataRecoveryHandler` verwenden können, müssen Sie [CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md) aufrufen.  
  
 Da die Klasse `CDataRecoveryHandler` eng an den Neustart\-Manager verbunden ist, hängt `CDataRecoveryHandler` vom globalen Parameter `m_dwRestartManagerSupportFlags` ab.  Dieser Parameter bestimmt, welche Berechtigungen der Neustart\-Manager hat und wie er auf die Anwendung interagiert.  Um den Neustart\-Manager in eine vorhandene Anwendung zu integrieren, müssen Sie `m_dwRestartManagerSupportFlags` den entsprechenden Wert im Konstruktor der Hauptanwendung zuweisen.  Weitere Informationen darüber, wie Sie den Neustart\-Manager, finden Sie unter [Gewusst wie: Hinzufügen von Unterstützung für den Neustart\-Manager](../../mfc/how-to-add-restart-manager-support.md) verwendet.  
  
## Anforderungen  
 **Header:** afxdatarecovery.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Gewusst wie: Hinzufügen von Unterstützung für den Neustart\-Manager](../../mfc/how-to-add-restart-manager-support.md)