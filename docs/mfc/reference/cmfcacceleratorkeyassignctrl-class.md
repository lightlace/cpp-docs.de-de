---
title: "CMFCAcceleratorKeyAssignCtrl Class"
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
  - "CMFCAcceleratorKeyAssignCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAcceleratorKeyAssignCtrl class"
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAcceleratorKeyAssignCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCAcceleratorKeyAssignCtrl`\-Klasse erweitert die [CEdit Class](../../mfc/reference/cedit-class.md), um zusätzliche Systemschaltflächen wie ALT, STRG und UMSCHALTTASTE zu unterstützen.  
  
## Syntax  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](../Topic/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl.md)|Erstellt ein `CMFCAcceleratorKeyAssignCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](../Topic/CMFCAcceleratorKeyAssignCtrl::GetAccel.md)|Ruft die `ACCEL`\-Struktur für eine im `CMFCAcceleratorKeyAssignCtrl`\-Objekt gedrückte Tastenkombination ab.|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](../Topic/CMFCAcceleratorKeyAssignCtrl::IsFocused.md)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](../Topic/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined.md)|Bestimmt, ob eine Tastenkombination definiert wurde.|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](../Topic/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage.md)|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md)\-Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows\-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden.  \(Überschreibt [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](../Topic/CMFCAcceleratorKeyAssignCtrl::ResetKey.md)|Setzt die Tastenkombination zurück.|  
  
## Hinweise  
 Diese Klasse erweitert die Funktionalität der `CEdit`\-Klasse, indem Sie Unterstützung von Tastenkombinationen hinzufügt, auch bekannt als Zugriffstasten.  Die `CMFCAcceleratorKeyAssignCtrl`\-Klasse funktioniert als [CEdit Class](../../mfc/reference/cedit-class.md) und kann Systemschaltflächen erkennen.  
  
 Diese Klasse ordnet Zeichenfolgenwerten physische Tastenkombinationen zu.  Angenommen die Tastenkombination ALT\+B ist der Zeichenfolge „Alt \+ B“ zugeordnet.  Wenn der Benutzer diese Tastenkombination in einem `CMFCAcceleratorKeyAssignCtrl`\-Objekt drückt, wird ihm „Alt\+B“ angezeigt.  Weitere Informationen zum Zuordnen von Tastenkombinationen und Zeichenfolgenformaten finden Sie unter [CMFCAcceleratorKey Class](../../mfc/reference/cmfcacceleratorkey-class.md).  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAcceleratorKeyAssignCtrl`\-Objekts und die Verwendung der `ResetKey`\-Methode zum Zurücksetzen der Tastenkombination.  
  
 [!CODE [NVC_MFC_RibbonApp#31](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#31)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)  
  
## Anforderungen  
 **Header:** afxacceleratorkeyassignctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCAcceleratorKey Class](../../mfc/reference/cmfcacceleratorkey-class.md)