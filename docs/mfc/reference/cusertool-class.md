---
title: "CUserTool Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserTool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserTool class"
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CUserTool Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt.  Die Registerkarte **Tools** des Dialogfelds **Anpassen** \([CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)\) ermöglicht es dem Benutzer, um Benutzertools hinzuzufügen, und den Namen, den Befehl, die Argumente und das Initialenverzeichnis für jedes Benutzertool anzugeben.  
  
## Syntax  
  
```  
class CUserTool : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](../Topic/CUserTool::CopyIconToClipboard.md)||  
|[CUserTool::DrawToolIcon](../Topic/CUserTool::DrawToolIcon.md)|Zeichnet das Benutzertoolsymbol in einem angegebenen Rechteck.|  
|[CUserTool::GetCommand](../Topic/CUserTool::GetCommand.md)|Gibt eine Zeichenfolge zurück, die den Text des Befehls enthält, der mit dem Benutzertool zugeordnet ist.|  
|[CUserTool::GetCommandId](../Topic/CUserTool::GetCommandId.md)|Gibt die Befehls\-ID des Menüelements des Benutzertools zurück.|  
|[CUserTool::Invoke](../Topic/CUserTool::Invoke.md)|Führt den Befehl aus, der der Benutzertool zugeordnet ist.|  
|[CUserTool::Serialize](../Topic/CUserTool::Serialize.md)|Liest oder Schreiben dieses Objekt von oder einem Archiv.  \(Überschreibungen [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CUserTool::SetCommand](../Topic/CUserTool::SetCommand.md)|Legt den Befehl fest, der mit dem Benutzertool zugeordnet ist.|  
|[CUserTool::SetToolIcon](../Topic/CUserTool::SetToolIcon.md)|Lädt das Symbol für das Benutzertool von der Anwendung, die mit dem Tool zugeordnet ist.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](../Topic/CUserTool::LoadDefaultIcon.md)|Lädt das Standardsymbol für ein Benutzertool.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CUserTool::m\_strArguments](../Topic/CUserTool::m_strArguments.md)|Die Befehlszeilenargumente für das Benutzertool.|  
|[CUserTool::m\_strInitialDirectory](../Topic/CUserTool::m_strInitialDirectory.md)|Das Ausgangsverzeichnis für das Benutzertool.|  
|[CUserTool::m\_strLabel](../Topic/CUserTool::m_strLabel.md)|Der Toolname, der im Menüelement für das Tool angezeigt wird.|  
  
## Hinweise  
 Weitere Informationen dazu, wie Sie Benutzertools in der Anwendung, finden Sie unter [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md) aktiviert.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Tool aus einem `CUserToolsManager`\-Objekt erstellt wird, dann die `m_strLabel`\-Membervariablen fest und für die Anwendung fest, die das Benutzertool ausführt.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#35](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#35)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## Anforderungen  
 **Header:** afxusertool.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)