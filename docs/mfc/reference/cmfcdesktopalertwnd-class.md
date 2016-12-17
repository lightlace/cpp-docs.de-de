---
title: "CMFCDesktopAlertWnd Class"
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
  - "CMFCDesktopAlertWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWnd class"
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCDesktopAlertWnd`\-Klasse implementiert die Funktionalität eines nicht modalen Dialogfelds, das auf dem Bildschirm angezeigt wird, den Benutzer über ein Ereignis zu informieren.  
  
## Syntax  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)|Erstellt und initialisiert das benutzerdefinierte TischplattenFenster.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::GetAnimationSpeed.md)|Gibt die Animationsgeschwindigkeit zurück.|  
|[CMFCDesktopAlertWnd::GetAnimationType](../Topic/CMFCDesktopAlertWnd::GetAnimationType.md)|Gibt den Animationstyp zurück.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::GetAutoCloseTime.md)|Gibt das automatisch geschlossene Timeout zurück.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](../Topic/CMFCDesktopAlertWnd::GetCaptionHeight.md)|Gibt die Höhe der Beschriftung zurück.|  
|[CMFCDesktopAlertWnd::GetDialogSize](../Topic/CMFCDesktopAlertWnd::GetDialogSize.md)||  
|[CMFCDesktopAlertWnd::GetLastPos](../Topic/CMFCDesktopAlertWnd::GetLastPos.md)|Gibt die letzte gültige Position des ausgewählten TischplattenFensters auf dem Bildschirm zurück.|  
|[CMFCDesktopAlertWnd::GetTransparency](../Topic/CMFCDesktopAlertWnd::GetTransparency.md)|Gibt die Transparenzebene zurück.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](../Topic/CMFCDesktopAlertWnd::HasSmallCaption.md)|Bestimmt, ob das benutzerdefinierte TischplattenFenster mit der kleinen Beschriftung angezeigt wird.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](../Topic/CMFCDesktopAlertWnd::OnBeforeShow.md)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](../Topic/CMFCDesktopAlertWnd::OnClickLinkButton.md)|Aufgerufen vom Framework, wenn der Benutzer auf eine Linkschaltfläche auf dem ausgewählten TischplattenMenü klickt.|  
|[CMFCDesktopAlertWnd::OnCommand](../Topic/CMFCDesktopAlertWnd::OnCommand.md)|Das Framework ruft diese Memberfunktion auf, wenn der Benutzer ein Element aus einem Menü ausgewählt wird, wenn ein untergeordnetes Steuerelement eine Benachrichtigung sendet oder wenn eine Zugriffstastentastatureingabe übersetzt wird.  \(Überschreibungen [CWnd::OnCommand](../Topic/CWnd::OnCommand.md).\)|  
|[CMFCDesktopAlertWnd::OnDraw](../Topic/CMFCDesktopAlertWnd::OnDraw.md)||  
|[CMFCDesktopAlertWnd::ProcessCommand](../Topic/CMFCDesktopAlertWnd::ProcessCommand.md)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md)|Legt die neue Animationsgeschwindigkeit fest.|  
|[CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md)|Legt den Animationstyp fest.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::SetAutoCloseTime.md)|Legt das automatisch geschlossene Timeout fest.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md)|Wechseln zwischen den kleinen und normalen Beschriftungen.|  
|[CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md)|Legt die Transparenzebene fest.|  
  
## Hinweise  
 Ein wachsames TischplattenFenster kann transparent, kann es mit Animationseffekten angezeigt werden, und es werden kann \(nach einer bestimmten Verzögerung oder, wenn der Benutzer es ablehnt, indem er auf die Schaltfläche "Schließen" klickt\).  
  
 Ein wachsames TischplattenFenster kann ein Standarddialogfeld auch enthalten, das wiederum ein Symbol, Meldungstext \(eine Bezeichnung\) und einen Link enthält.  Alternativ kann ein wachsames TischplattenFenster ein benutzerdefiniertes Dialogfeld von Ressourcen der Anwendung enthalten.  
  
 Sie erstellen ein wachsames TischplattenFenster in zwei Schritten erstellt.  Zuerst rufen Sie den Konstruktor auf, um das `CMFCDesktopAlertWnd`\-Objekt zu erstellen.  Zweitens [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) rufen Sie die Memberfunktion auf, um das Fenster zu erstellen und auf den `CMFCDesktopAlertWnd`\-Objekt anzufügen.  
  
 Das Objekt stellt `CMFCDesktopAlertWnd` ein bestimmtes untergeordnetes Dialogfeld erstellt, das den Clientbereich des ausgewählten TischplattenFensters ausfüllt.  Das Dialogfeld besitzt alle Steuerelemente, die auf ihm positioniert werden.  
  
 Um ein benutzerdefiniertes Dialogfeld auf dem Popupfenster anzuzeigen, führen Sie folgende Schritte aus:  
  
1.  Leiten Sie eine Klasse von `CMFCDesktopAlertDialog` ab.  
  
2.  Erstellen Sie eine untergeordnete Dialogfeldvorlage in Ressourcen.  
  
3.  Rufen Sie [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) mithilfe des Ressourcen\-ID der Dialogfeldvorlage und den Zeiger auf das Ablaufklasseninformationen der abgeleiteten Klasse auf.  
  
4.  Programmieren Sie das benutzerdefinierte Dialogfeld, um alle Benachrichtigungen zu bearbeiten, die von den gehosteten Steuerelementen, stammen oder programmieren Sie die gehosteten Steuerelemente, um diese Benachrichtigungen direkt zu bearbeiten.  
  
 Verwenden Sie die folgenden Funktionen, um das Verhalten des Desktopwarnungsfensters zu steuern:  
  
-   Legen Sie den Animationstyp fest, indem Sie [CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md) aufriefen.  Gültiges Optionseinschliessung falten auf, schieben und blenden aus.  
  
-   Legen Sie die Animationsframegeschwindigkeit fest, indem Sie [CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md) aufriefen.  
  
-   Legen Sie die Transparenz fest, indem Sie [CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md) glätten, aufriefen.  
  
-   Ändern Sie die Größe der Beschriftung zu kleinem, indem Sie [CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md) aufrufen.  Die kleine Beschriftung ist 7 Pixel hoch.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie verschiedene Methoden in der `CMFCDesktopAlertWnd`\-Klasse verwendet, um ein `CMFCDesktopAlertWnd`\-Objekt zu konfigurieren.  Im Beispiel wird gezeigt, wie ein Animationstyp, legen Sie die Transparenz des Popupfensters, angeben, dass das Warnungsereignisse Fenster eine kleine Beschriftung anzeigt, und legen die Zeit festgelegt wird, die Verläufe vor dem Warnmeldungsfenster automatisch geschlossen wird.  Das Beispiel zeigt auch, wie das benutzerdefinierte TischplattenFenster erstellt und initialisiert.  Dieser Codeausschnitt ist Teil [Desktop\-wachsames Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DesktopAlertDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DesktopAlertDemo#1)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## Anforderungen  
 **Header:** afxDesktopAlertWnd.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo Class](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)