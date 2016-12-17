---
title: "CFontDialog Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CFontDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontDialog class"
  - "Dialogfelder, Schriftarten"
  - "Schriftarten"
  - "Schriftarten, Auswählen"
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CFontDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es Ihnen, ein SchriftartAuswahl Dialogfeld in Ihre Anwendung zu speichern.  
  
## Syntax  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](../Topic/CFontDialog::CFontDialog.md)|Erstellt ein `CFontDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFontDialog::DoModal](../Topic/CFontDialog::DoModal.md)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer, um die Auswahl zu machen.|  
|[CFontDialog::GetCharFormat](../Topic/CFontDialog::GetCharFormat.md)|Ruft die Zeichenformatierung der ausgewählten Schriftarten ab.|  
|[CFontDialog::GetColor](../Topic/CFontDialog::GetColor.md)|Gibt die Farbe der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetCurrentFont](../Topic/CFontDialog::GetCurrentFont.md)|Weist die Eigenschaften der ausgewählten Schriftarten zu einer `LOGFONT`\-Struktur zu.|  
|[CFontDialog::GetFaceName](../Topic/CFontDialog::GetFaceName.md)|Gibt den Flächennamen der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetSize](../Topic/CFontDialog::GetSize.md)|Gibt den Schriftgrad der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetStyleName](../Topic/CFontDialog::GetStyleName.md)|Gibt den Formatnamen der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetWeight](../Topic/CFontDialog::GetWeight.md)|Gibt die Gewichtung der ausgewählten Schriftart zurück.|  
|[CFontDialog::IsBold](../Topic/CFontDialog::IsBold.md)|Bestimmt, ob die Schriftart fett formatiert ist.|  
|[CFontDialog::IsItalic](../Topic/CFontDialog::IsItalic.md)|Bestimmt, ob die Schriftart kursiv formatiert ist.|  
|[CFontDialog::IsStrikeOut](../Topic/CFontDialog::IsStrikeOut.md)|Bestimmt, ob die Schriftart mit Durchgestrichen angezeigt wird.|  
|[CFontDialog::IsUnderline](../Topic/CFontDialog::IsUnderline.md)|Bestimmt, ob die Schriftart unterstrichen ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFontDialog::m\_cf](../Topic/CFontDialog::m_cf.md)|Eine Struktur verwendet, um ein `CFontDialog`\-Objekt anzupassen.|  
  
## Hinweise  
 Ein Objekt `CFontDialog` ist ein Dialogfeld mit einer Liste von Schriftarten, die derzeit im System.  Der Benutzer kann eine bestimmte Schriftart aus der Liste auswählen, und diese Auswahl wird dann in der Anwendung ausgegeben.  
  
 So fügen Sie ein `CFontDialog`\-Objekt erstellen, den bereitgestellten Konstruktor verwenden oder eine neue Unterklasse berechnen und den eigenen benutzerdefinierten Konstruktor verwenden.  
  
 Sobald ein `CFontDialog`\-Objekt erstellt wurde, können Sie die `m_cf`\-Struktur verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die [m\_cf](../Topic/CFontDialog::m_cf.md)\-Struktur ist vom Typ [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832).  Weitere Informationen über diese Struktur, finden Sie unter [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Nachdem Sie die Steuerelemente des Dialogfeldobjekts initialisiert haben, rufen Sie die `DoModal`\-Memberfunktion auf, um das Dialogfeld anzuzeigen und dem Benutzer zu ermöglichen, eine Schriftart auswählen.  `DoModal` gibt zurück, ob der Benutzer OK \(**IDOK**\) oder Schaltfläche Löschverhalten \(**IDCANCEL**\) ausgewählt hat.  
  
 Wenn `DoModal`**IDOK** zurückgibt, können Sie eine der Memberfunktionen von `CFontDialog` verwenden, um die Informationseingabe durch den Benutzer abzurufen.  
  
 Sie können die Funktion Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) verwenden, um mehr über den Fehler zu ermitteln, ob ein Fehler aufgetreten ist während der Initialisierung des Dialogfelds und zu erfahren.  Weitere Informationen zu dieser Funktion finden Sie unter, [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CFontDialog` beruht auf der COMMDLG.DLL\-Datei, die mit Windows\-Versionen 3,1 und höher bereitgestellt wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFontDialog`, erstellen Sie eine benutzerdefinierte Dialogfeldvorlage, und fügen Sie eine Meldungszuordnung hinzu um die Benachrichtigungsmeldungen aus den erweiterten \- Steuerelementen verarbeiten.  Alle nicht verarbeiteten Nachrichten sollten die Basisklasse übergeben werden.  
  
 Die Hookfunktion anzupassen ist nicht erforderlich.  
  
 Weitere Informationen zur Verwendung von `CFontDialog`, finden Sie unter [Allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [MFC Sampling HIERSVR](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)