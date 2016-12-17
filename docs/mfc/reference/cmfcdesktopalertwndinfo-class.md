---
title: "CMFCDesktopAlertWndInfo Class"
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
  - "CMFCDesktopAlertWndInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndInfo class"
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWndInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCDesktopAlertWndInfo`\-Klasse wird mit dem [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md) verwendet.  Sie gibt die Steuerelemente, die angezeigt werden, wenn das Desktopwarnungsfenster angezeigt wird.  
  
## Syntax  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator\=](../Topic/CMFCDesktopAlertWndInfo::operator=.md)||  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md)|Ein Handle für das Symbol, das angezeigt wird.|  
|[CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md)|Die Befehls\-ID zugeordnet mit einem Link auf dem ausgewählten TischplattenFenster.|  
|[CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md)|Der Text, der auf dem ausgewählten TischplattenFenster angezeigt wird.|  
|[CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md)|Der Link, der auf dem ausgewählten TischplattenFenster angezeigt wird.|  
  
## Hinweise  
 Die `CMFCDesktopAlertWndInfo`\-Klasse wird zur [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)\-Methode übergeben, um die Elemente anzugeben, die auf dem Standard Dialogfeld des Desktopwarnungsfensters angezeigt werden.  Das standardmäßige Dialogfeld kann drei Elemente enthalten:  
  
-   Ein Symbol, das festgelegt wird, indem [CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md) aufruft.  
  
-   Eine Bezeichnung oder Textmeldung, die festgelegt wird, indem [CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md) aufruft.  
  
-   Ein Link, der festgelegt wird, indem [CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md) aufruft.  Um den Befehl festzulegen der ausgeführt wird wenn auf den Link geklickt wird, rufen Sie [CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md) auf.  
  
 Wenn das Standarddialogfeld nicht ausreichend ist, können Sie ein benutzerdefiniertes Dialogfeld erstellen und an die Methode übergeben, [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md), anstatt diese Klasse zu verwenden.  Weitere Informationen finden Sie unter [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Member in der `CMFCDesktopAlertWndInfo`\-Klasse verwendet.  Das Beispiel zeigt, wie das Handle für das Symbol, das angezeigt wird, der Text festlegen, der auf dem ausgewählten TischplattenFenster, dem Link, der auf dem ausgewählten TischplattenFenster angezeigt wird und der Befehls\-ID angezeigt wird, die mit einem Link auf dem ausgewählten TischplattenFenster zugeordnet ist.  Dieses Beispiel ist Teil [Desktop\-wachsames Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DesktopAlertDemo#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DesktopAlertDemo#3)]  
  
## Vererbungshierarchie  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## Anforderungen  
 **Header:** afxDesktopAlertDialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)