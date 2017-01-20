---
title: "CMFCWindowsManagerDialog Class"
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
  - "CMFCWindowsManagerDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCWindowsManagerDialog class"
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCWindowsManagerDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Objekt `CMFCWindowsManagerDialog` ermöglicht es einem Benutzer, um untergeordnete MDI\-Fenster in einer MDI\-Anwendung zu verwalten.  
  
## Syntax  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](../Topic/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog.md)|Erstellt ein `CMFCWindowsManagerDialog`\-Objekt.|  
  
## Hinweise  
 `CMFCWindowsManagerDialog` enthält eine Liste von untergeordneten MDI\-Fenstern, die in der Anwendung geöffnet sind.  Der Benutzer kann den Zustand der untergeordneten MDI\-Fenster manuell steuern, indem er dieses Dialogfeld verwendet.  
  
 `CMFCWindowsManagerDialog` wird innerhalb [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md) eingebettet.  `CMFCWindowsManagerDialog` ist keine Klasse, die Sie manuell erstellen möchten.  Rufen Sie die Funktion [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md) auf, und sie erstellt und zeigt ein `CMFCWindowsManagerDialog`\-Objekt.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCWindowsManagerDialog`\-Objekt erstellt, indem es `CMDIFrameWndEx::ShowWindowsDialog` aufruft.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#18](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#18)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## Anforderungen  
 **Header:** afxWindowsManagerDialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md)   
 [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)