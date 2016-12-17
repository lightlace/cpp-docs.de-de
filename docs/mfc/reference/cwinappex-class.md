---
title: "CWinAppEx Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CWinAppEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinAppEx class"
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# CWinAppEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWinAppEx` behandelt den Anwendungszustand, speichert den Zustand in die Registrierung, lädt den Zustand aus der Registrierung, initialisiert Anwendungsmanager und Links zu den gleichen Anwendungsmanagern bereit.  
  
## Syntax  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinAppEx::CWinAppEx](../Topic/CWinAppEx::CWinAppEx.md)|Erstellt ein `CWinAppEx`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinAppEx::CleanState](../Topic/CWinAppEx::CleanState.md)|Entfernt Informationen zur Verwendung von der Windows\-Registrierung.|  
|[CWinAppEx::EnableLoadWindowPlacement](../Topic/CWinAppEx::EnableLoadWindowPlacement.md)|Gibt an, ob die Anwendung die ursprüngliche Größe und die Position des Hauptrahmenfensters aus der Registrierung lädt.|  
|[CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md)|Ermöglicht Tearoffe Menüs für die Anwendung.|  
|[CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md)|Ermöglicht den Benutzern, um Befehle des benutzerdefinierten Menüs in der Anwendung zu erstellen.|  
|[CWinAppEx::ExitInstance](../Topic/CWinAppEx::ExitInstance.md)|Aufgerufen durch das Framework aus der `Run`\-Memberfunktion, um diese Instanz der Anwendung zu beenden.  \(Überschreibungen [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md).\)|  
|[CWinAppEx::GetBinary](../Topic/CWinAppEx::GetBinary.md)|Liest Binärdaten, die mit dem angegebenen Registrierungswert zugeordnet ist.|  
|[CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md)|Gibt einen Zeiger auf [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) globalen Objekt zurück.|  
|[CWinAppEx::GetDataVersion](../Topic/CWinAppEx::GetDataVersion.md)||  
|[CWinAppEx::GetDataVersionMajor](../Topic/CWinAppEx::GetDataVersionMajor.md)|Gibt die Hauptversion der Anwendung zurück, die in der Windows\-Registrierung gespeichert wird.|  
|[CWinAppEx::GetDataVersionMinor](../Topic/CWinAppEx::GetDataVersionMinor.md)|Gibt die Nebenversion der Anwendung zurück, die in der Windows\-Registrierung gespeichert wird.|  
|[CWinAppEx::GetInt](../Topic/CWinAppEx::GetInt.md)|Liest numerische Daten, die mit dem angegebenen Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md)|Gibt einen Zeiger auf [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) globalen Objekt zurück.|  
|[CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md)|Gibt einen Zeiger auf [CMouseManager](../../mfc/reference/cmousemanager-class.md) globalen Objekt zurück.|  
|[CWinAppEx::GetObject](../Topic/CWinAppEx::GetObject.md)|Liest `CObject` von abgeleitete Daten, die mit dem angegebenen Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetRegSectionPath](../Topic/CWinAppEx::GetRegSectionPath.md)|Gibt eine Zeichenfolge zurück, die der Pfad eines Registrierungsschlüssels ist.  Dieser Pfad verkettet den angegebenen relativen Pfad mit dem Anwendungspfad.|  
|[CWinAppEx::GetRegistryBase](../Topic/CWinAppEx::GetRegistryBase.md)|Gibt den Registrierungspfad für die Anwendung zurück.|  
|[CWinAppEx::GetSectionBinary](../Topic/CWinAppEx::GetSectionBinary.md)|Liest Binärdaten, die dem angegebenen Schlüssel und dem Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetSectionInt](../Topic/CWinAppEx::GetSectionInt.md)|Liest numerische Daten aus der Registrierung, die dem angegebenen Schlüssel und dem Wert zugeordnet ist.|  
|[CWinAppEx::GetSectionObject](../Topic/CWinAppEx::GetSectionObject.md)|Liest `CObject` Daten, die dem angegebenen Schlüssel und dem Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetSectionString](../Topic/CWinAppEx::GetSectionString.md)|Liest Zeichenfolgendaten, die dem angegebenen Schlüssel und dem Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md)|Gibt einen Zeiger auf [CShellManager](../../mfc/reference/cshellmanager-class.md) globalen Objekt zurück.|  
|[CWinAppEx::GetString](../Topic/CWinAppEx::GetString.md)|Liest Zeichenfolgendaten, die mit dem angegebenen Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetTooltipManager](../Topic/CWinAppEx::GetTooltipManager.md)|Gibt einen Zeiger auf [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) globalen Objekt zurück.|  
|[CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md)|Gibt einen Zeiger auf [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) globalen Objekt zurück.|  
|[CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)|Initialisiert das `CContextMenuManager`\-Objekt.|  
|[CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)|Initialisiert das `CKeyboardManager`\-Objekt.|  
|[CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md)|Initialisiert das `CMouseManager`\-Objekt.|  
|[CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md)|Initialisiert die `CShellManager`\-Klasse|  
|[CWinAppEx::InitTooltipManager](../Topic/CWinAppEx::InitTooltipManager.md)|Initialisiert die `CTooltipManager`\-Klasse.|  
|[CWinAppEx::IsResourceSmartUpdate](../Topic/CWinAppEx::IsResourceSmartUpdate.md)||  
|[CWinAppEx::IsStateExists](../Topic/CWinAppEx::IsStateExists.md)|Gibt an, ob der angegebene Schlüssel in der Registrierung ist.|  
|[CWinAppEx::LoadState](../Topic/CWinAppEx::LoadState.md)|Lädt den Anwendungszustand aus der Registrierung.|  
|[CWinAppEx::OnAppContextHelp](../Topic/CWinAppEx::OnAppContextHelp.md)|Aufgerufen vom Framework wenn die Benutzeranforderungskontexthilfe für das Dialogfeld **Anpassung**.|  
|[CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)|Ruft den benutzerdefinierten Befehl auf, wenn der Benutzer auf eine beliebige Stelle in der Anwendung doppelklickt.|  
|[CWinAppEx::OnWorkspaceIdle](../Topic/CWinAppEx::OnWorkspaceIdle.md)||  
|[CWinAppEx::SaveState](../Topic/CWinAppEx::SaveState.md)|Schreibt den Zustand des Anwendungsframeworks zur Windows\-Registrierung.|  
|[CWinAppEx::SetRegistryBase](../Topic/CWinAppEx::SetRegistryBase.md)|Legt den Pfad des standardmäßigen Registrierungsschlüssel fest.  Dieser Schlüssel dient als Stamm für alle folgenden Registrierungsaufrufe.|  
|[CWinAppEx::ShowPopupMenu](../Topic/CWinAppEx::ShowPopupMenu.md)|Zeigt ein Popupmenü an.|  
|[CWinAppEx::WriteBinary](../Topic/CWinAppEx::WriteBinary.md)|Schreibt die Binärdaten zum angegebenen Registrierungswert.|  
|[CWinAppEx::WriteInt](../Topic/CWinAppEx::WriteInt.md)|Schreibt die numerischen Daten zum angegebenen Registrierungswert.|  
|[CWinAppEx::WriteObject](../Topic/CWinAppEx::WriteObject.md)|Schreibt Daten, die von [CObject Class](../../mfc/reference/cobject-class.md) zum angegebenen Registrierungswert abgeleitet wird.|  
|[CWinAppEx::WriteSectionBinary](../Topic/CWinAppEx::WriteSectionBinary.md)|Schreibt die Binärdaten zu einem Wert des angegebenen Registrierungsschlüssels.|  
|[CWinAppEx::WriteSectionInt](../Topic/CWinAppEx::WriteSectionInt.md)|Schreibt die numerischen Daten in einen Wert des angegebenen Registrierungsschlüssels.|  
|[CWinAppEx::WriteSectionObject](../Topic/CWinAppEx::WriteSectionObject.md)|Schreibt die Daten, die von der `CObject`\-Klasse in einen Wert des angegebenen Registrierungsschlüssels abgeleitet werden.|  
|[CWinAppEx::WriteSectionString](../Topic/CWinAppEx::WriteSectionString.md)|Schreibt die Zeichenfolgendaten zu einem Wert des angegebenen Registrierungsschlüssels.|  
|[CWinAppEx::WriteString](../Topic/CWinAppEx::WriteString.md)|Schreibt die Zeichenfolgendaten zum angegebenen Registrierungswert.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinAppEx::LoadCustomState](../Topic/CWinAppEx::LoadCustomState.md)|Aufgerufen vom Framework, wenn der Anwendungszustand geladen wurde.|  
|[CWinAppEx::LoadWindowPlacement](../Topic/CWinAppEx::LoadWindowPlacement.md)|Aufgerufen vom Framework, wenn die Größe und Position der Anwendung aus der Registrierung lädt.  Die geladenen Daten enthalten die Größe und die Position des Großrechners, als das Anwendungsletztes geschlossen hat.|  
|[CWinAppEx::OnClosingMainFrame](../Topic/CWinAppEx::OnClosingMainFrame.md)|Aufgerufen vom Framework ausgelöst, wenn ein Hauptrahmenfenster `WM_CLOSE` verarbeitet.|  
|[CWinAppEx::PreLoadState](../Topic/CWinAppEx::PreLoadState.md)|Aufgerufen vom Framework direkt vor dem Anwendungszustand wird geladen.|  
|[CWinAppEx::PreSaveState](../Topic/CWinAppEx::PreSaveState.md)|Aufgerufen vom Framework direkt vor dem Anwendungszustand wird gespeichert.|  
|[CWinAppEx::ReloadWindowPlacement](../Topic/CWinAppEx::ReloadWindowPlacement.md)|Lädt die Größe und Position des angegebenen Fensters aus der Registrierung erneut|  
|[CWinAppEx::SaveCustomState](../Topic/CWinAppEx::SaveCustomState.md)|Aufgerufen vom Framework, nachdem der Anwendungszustand zur Registrierung schreibt.|  
|[CWinAppEx::StoreWindowPlacement](../Topic/CWinAppEx::StoreWindowPlacement.md)|Aufgerufen vom Framework, um die Größe und die Position des Großrechners zur Registrierung zu schreiben.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CWinAppEx::m\_bForceImageReset](../Topic/CWinAppEx::m_bForceImageReset.md)|Gibt an, ob das Framework alle Symbolleistenimages zurücksetzt, wenn das Rahmenfenster, das die Symbolleiste enthält, geladen wird.|  
  
## Hinweise  
 Ein Großteil der Funktionalität, die vom MFC\-Framework bereitgestellt wird, hängt von der `CWinAppEx`\-Klasse ab.  Sie können die `CWinAppEx`\-Klasse in die Anwendung in einer von zwei Methoden enthalten:  
  
-   Erstellen Sie eine Klasse `CWinAppEx` im Hauptthread.  
  
-   Leiten Sie die Hauptanwendungsklasse von `CWinAppEx`.  
  
 Nachdem Sie `CWinAppEx` in eine Anwendung integrieren, können Sie einen der Anwendungsmanager initialisieren.  Bevor Sie einen Anwendungsmanager verwenden, müssen Sie sie initialisieren, indem Sie die entsprechende Initialisierungsmethode aufrufen.  Um ein Zeiger auf einen bestimmten Manager zu erhalten, rufen Sie das zugeordnete abrufen Methode auf.  Die `CWinAppEx`\-Klasse verwaltet die folgenden Anwendungsmanager: [CMouseManager Class](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md) und [CMenuTearOffManager Class](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## Anforderungen  
 **Header:** afxwinappex.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager Class](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)