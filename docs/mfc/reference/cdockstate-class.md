---
title: "CDockState Class"
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
  - "CDockState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockState class"
  - "dock state"
  - "docking control bars"
  - "docking tool windows"
  - "Position, control bar"
  - "Größe"
  - "Größe, control bar"
  - "Zustände, dockable control bar"
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CDockState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die `CObject` serialisierte lädt, nimmt entladen oder löscht den Zustand einer oder mehrerer Steuerleisten Andocken im persistenten Speicher \(eine Datei\).  
  
## Syntax  
  
```  
class CDockState : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDockState::Clear](../Topic/CDockState::Clear.md)|Löscht die Dockzustandsinformationen.|  
|[CDockState::GetVersion](../Topic/CDockState::GetVersion.md)|Ruft die Versionsnummer der gespeicherten Leistezustandes ab.|  
|[CDockState::LoadState](../Topic/CDockState::LoadState.md)|Ruft Zustandsinformationen aus der Registrierung oder der INI\-Datei ab.|  
|[CDockState::SaveState](../Topic/CDockState::SaveState.md)|Speichert Zustandsinformationen zur Registrierung oder die INI\-Datei.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDockState::m\_arrBarInfo](../Topic/CDockState::m_arrBarInfo.md)|Array von Zeigern auf gespeicherte Dockzustandsinformationen mit einem Eintrag für jede Steuerleiste.|  
  
## Hinweise  
 Der Dockzustand enthält die Größe und Position der Leiste und ob er angedockt ist.  Wenn der gespeicherten Dockzustand `CDockState` überprüft, der die Position und abgerufen werden, wenn die Leiste nicht mit den aktuellen Bildschirmeinstellungen sichtbar ist, `CDockState` Leiste skaliert die Position der Leiste, damit sie sichtbar ist.  Der Hauptzweck `CDockState` ist, den gesamten Zustand mehrerer Steuerleisten angehalten und gespeichert werden Zustand zu ermöglichen, diesen und hat entweder zur Registrierung, die INI\-Datei der Anwendung oder in binärer Form als Teil des Inhalts eines `CArchive`\-Objekts.  
  
 Die Leiste kann eine andockbare Symbolleisten, einschließlich eine Symbolleiste, eine Statusleiste oder eine Dialogleiste sein.  `CDockState`\-Objekte werden und Lesen zu oder von einer Datei zu einem `CArchive`\-Objekt geschrieben.  
  
 [CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md) ruft die Zustandsinformationen `CControlBar` des gesamten Rahmenfensters Objekte und setzt sie in das `CDockState`\-Objekt ab.  Sie können den Inhalt des `CDockState`\-Objekts in den Speicher mit [Serialisieren Sie](../Topic/CObject::Serialize.md) oder [CDockState::SaveState](../Topic/CDockState::SaveState.md) schreiben.  Wenn Sie später den Zustand der Steuerleisten im Rahmenfenster wiederherstellen möchten, können Sie den Zustand mit `Serialize` oder [CDockState::LoadState](../Topic/CDockState::LoadState.md) laden, verwenden [CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md), um den gespeicherten Zustand zu den Steuerleisten des Rahmenfensters anzuwenden.  
  
 Weitere Informationen zu andockbare Steuerleisten, finden Sie in Artikel [Steuerleisten](../../mfc/control-bars.md), [Symbolleisten: Andock und unverankert](../../mfc/docking-and-floating-toolbars.md) und [Rahmenfenster](../../mfc/frame-windows.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## Anforderungen  
 **Header:** afxadv.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)