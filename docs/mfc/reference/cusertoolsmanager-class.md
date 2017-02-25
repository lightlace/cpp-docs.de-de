---
title: "CUserToolsManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserToolsManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserToolsManager class"
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CUserToolsManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Behält die Auflistung von [CUserTool Class](../../mfc/reference/cusertool-class.md)\-Objekten in einer Anwendung zu.  Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt.  Das Objekt `CUserToolsManager` können Benutzer oder den Entwickler, um neue Benutzertools der Anwendung hinzuzufügen.  Sie unterstützt die Ausführung der Befehle, die mit Benutzertools zugeordnet werden, und es werden außerdem Informationen über Benutzertools in der Windows\-Registrierung.  
  
## Syntax  
  
```  
class CUserToolsManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](../Topic/CUserToolsManager::CUserToolsManager.md)|Erstellt einen `CUserToolsManager`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md)|Stellt ein neues Benutzertool erstellt.|  
|[CUserToolsManager::FindTool](../Topic/CUserToolsManager::FindTool.md)|Gibt den Zeiger auf das `CMFCUserTool`\-Objekt zurück, das einer angegebenen Befehl ID zugeordnet ist|  
|[CUserToolsManager::GetArgumentsMenuID](../Topic/CUserToolsManager::GetArgumentsMenuID.md)|Gibt die ID der Ressource zurück, das mit dem Menü **Argumente** auf der Registerkarte des Dialogfelds **ToolsAnpassen** zugeordnet ist.|  
|[CUserToolsManager::GetDefExt](../Topic/CUserToolsManager::GetDefExt.md)|Gibt die standardmäßige Erweiterung zurück, die das **Datei öffnen** \(Dialogfeld [CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)\) auf dem Feld **Befehl** auf der Registerkarte des Dialogfelds **ToolsAnpassen** verwendet.|  
|[CUserToolsManager::GetFilter](../Topic/CUserToolsManager::GetFilter.md)|Gibt den Dateifilter zurück, den das **Datei öffnen** \(Dialogfeld [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) auf dem Feld **Befehl** auf der Registerkarte des Dialogfelds **ToolsAnpassen** verwendet.|  
|[CUserToolsManager::GetInitialDirMenuID](../Topic/CUserToolsManager::GetInitialDirMenuID.md)|Gibt die ID der Ressource zurück, das mit dem Menü **Ausgangsverzeichnis** auf der Registerkarte des Dialogfelds **ToolsAnpassen** zugeordnet ist.|  
|[CUserToolsManager::GetMaxTools](../Topic/CUserToolsManager::GetMaxTools.md)|Gibt die maximale Anzahl von Benutzertools zurück, die in der Anwendung zugeordnet werden können.|  
|[CUserToolsManager::GetToolsEntryCmd](../Topic/CUserToolsManager::GetToolsEntryCmd.md)|Gibt die Befehls\-ID des Menüelementplatzhalters für Benutzertools zurück.|  
|[CUserToolsManager::GetUserTools](../Topic/CUserToolsManager::GetUserTools.md)|Gibt einen Verweis auf die Liste der Benutzertools zurück.|  
|[CUserToolsManager::InvokeTool](../Topic/CUserToolsManager::InvokeTool.md)|Führt eine Anwendung aus, die dem Benutzertool zugeordnet, das eine angegebene Befehl ID besitzt|  
|[CUserToolsManager::IsUserToolCmd](../Topic/CUserToolsManager::IsUserToolCmd.md)|Bestimmt, ob eine Befehls\-ID mit einem Benutzertool zugeordnet ist.|  
|[CUserToolsManager::LoadState](../Topic/CUserToolsManager::LoadState.md)|Lädt Informationen über Benutzertools aus der Windows\-Registrierung.|  
|[CUserToolsManager::MoveToolDown](../Topic/CUserToolsManager::MoveToolDown.md)|Verschiebt das angegebene Benutzertool unten in der Liste der Benutzertools.|  
|[CUserToolsManager::MoveToolUp](../Topic/CUserToolsManager::MoveToolUp.md)|Verschiebt das angegebene Benutzertool oben in der Liste der Benutzertools.|  
|[CUserToolsManager::RemoveTool](../Topic/CUserToolsManager::RemoveTool.md)|Entfernt das angegebene Benutzertool von der Anwendung.|  
|[CUserToolsManager::SaveState](../Topic/CUserToolsManager::SaveState.md)|Speichert Informationen über Benutzertools in der Windows\-Registrierung.|  
|[CUserToolsManager::SetDefExt](../Topic/CUserToolsManager::SetDefExt.md)|Gibt die standardmäßige Erweiterung an, die das **Datei öffnen** \(Dialogfeld [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) auf dem Feld **Befehl** auf der Registerkarte des Dialogfelds **ToolsAnpassen** verwendet.|  
|[CUserToolsManager::SetFilter](../Topic/CUserToolsManager::SetFilter.md)|Gibt den Dateifilter an, den das **Datei öffnen** \(Dialogfeld [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) auf dem Feld **Befehl** auf der Registerkarte des Dialogfelds **ToolsAnpassen** verwendet.|  
  
## Hinweise  
 So Benutzertools in eine Anwendung integrieren, müssen Sie:  
  
 1.  Reservieren Sie ein Menüelement und eine zugeordnete Befehls\-ID für einen Benutzertool\-Menüeintrag.  
  
 2.  Reservieren Sie eine sequenzielle Befehls\-ID für jedes Benutzertool, das der Benutzer in der Anwendung definieren kann.  
  
 3.  Rufen Sie die [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md)\-Methode auf und geben Sie die folgenden Parameter: Menübefehl ID, Benutzertoolbefehls\-id erste und letzte Benutzertoolbefehl ID  
  
 Es sollte nur ein globales Objekt `CUserToolsManager` pro Anwendung geben.  
  
 Ein Beispiel für die Benutzertools, finden Sie das VisualStudioDemo\-Beispiel zu projizieren.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Verweis auf ein `CUserToolsManager`\-Objekt abgerufen wird und wie neue Benutzertools erstellt wird.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#38](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#38)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)  
  
## Anforderungen  
 **Header:** afxusertoolsmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserTool Class](../../mfc/reference/cusertool-class.md)