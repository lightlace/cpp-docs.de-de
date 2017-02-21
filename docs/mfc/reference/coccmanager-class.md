---
title: "COccManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COccManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelementcontainer [C++], control site"
  - "CNoTrackObject class"
  - "COccManager class"
  - "Benutzerdefinierte Steuerelemente [MFC], sites"
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# COccManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet andere Sites des benutzerdefinierten Steuerelements; implementiert wird `COleControlContainer` und `COleControlSite`\-Objekte.  
  
## Syntax  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COccManager::CreateContainer](../Topic/COccManager::CreateContainer.md)|Erstellt ein Objekt **COleContainer**.|  
|[COccManager::CreateDlgControls](../Topic/COccManager::CreateDlgControls.md)|Erstellt, ActiveX\-Steuerelemente, die durch das zugeordnete Objekt `COleContainer` gehostet sind.|  
|[COccManager::CreateSite](../Topic/COccManager::CreateSite.md)|Erstellt ein `COleClientSite`\-Objekt.|  
|[COccManager::GetDefBtnCode](../Topic/COccManager::GetDefBtnCode.md)|Ruft den Code der Standardschaltfläche ab.|  
|[COccManager::IsDialogMessage](../Topic/COccManager::IsDialogMessage.md)|Bestimmt das Ziel einer Dialognachricht.|  
|[COccManager::IsLabelControl](../Topic/COccManager::IsLabelControl.md)|Bestimmt, ob das angegebene Steuerelement ein Label\-Steuerelement ist.|  
|[COccManager::IsMatchingMnemonic](../Topic/COccManager::IsMatchingMnemonic.md)|Bestimmt, ob die Strommnemotechnik die Zugriffs\- des angegebenen Steuerelements übereinstimmt.|  
|[COccManager::OnEvent](../Topic/COccManager::OnEvent.md)|versucht, die angegebene Ereignis zu behandeln.|  
|[COccManager::PostCreateDialog](../Topic/COccManager::PostCreateDialog.md)|Gibt die Ressourcen frei, die während der Dialogfelderstellung zugeordnet werden.|  
|[COccManager::PreCreateDialog](../Topic/COccManager::PreCreateDialog.md)|Verarbeitet eine Dialogfeldvorlage für ActiveX\-Steuerelemente.|  
|[COccManager::SetDefaultButton](../Topic/COccManager::SetDefaultButton.md)|Schaltet den Standardzustand des angegebenen Steuerelements um.|  
|[COccManager::SplitDialogTemplate](../Topic/COccManager::SplitDialogTemplate.md)|Trennt alle vorhandenen ActiveX\-Steuerelemente von den allgemeinen Steuerelementen in der angegebenen Dialogfeldvorlage.|  
  
## Hinweise  
 Die Basisklasse, **CNoTrackObject**, ist eine nicht dokumentierte Basisklasse \(in AFXTLS.H\).  Ist für das MFC\-Framework, sind Klassen, die von der **CNoTrackObject**\-Klasse abgeleitet werden, von der Speicherverlusterkennung außer.  Es wird nicht empfohlen, direkt aus **CNoTrackObject** berechnen.  
  
## Vererbungshierarchie  
 `CNoTrackObject`  
  
 `COccManager`  
  
## Anforderungen  
 **Header:** afxocc.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)