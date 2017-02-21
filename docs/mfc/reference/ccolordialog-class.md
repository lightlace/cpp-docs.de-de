---
title: "CColorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColorDialog class"
  - "Farben, Dialogfeld"
  - "Dialogfelder, Farben"
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es Ihnen, ein FarbeAuswahl Dialogfeld in Ihre Anwendung zu speichern.  
  
## Syntax  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](../Topic/CColorDialog::CColorDialog.md)|Erstellt ein `CColorDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CColorDialog::DoModal](../Topic/CColorDialog::DoModal.md)|Zeigt ein Dialogfeld an und ermöglicht dem Benutzer, um die Auswahl zu machen.|  
|[CColorDialog::GetColor](../Topic/CColorDialog::GetColor.md)|Gibt eine **COLORREF**\-Struktur zurück, die die Werte der ausgewählten Farbe enthält.|  
|[CColorDialog::GetSavedCustomColors](../Topic/CColorDialog::GetSavedCustomColors.md)|Ruft die benutzerdefinierten Farben ab, die vom Benutzer erstellt werden.|  
|[CColorDialog::SetCurrentColor](../Topic/CColorDialog::SetCurrentColor.md)|Erzwingt die aktuelle Farbauswahl der angegebenen Farbe.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](../Topic/CColorDialog::OnColorOK.md)|Überschreiben Sie, um die Farbe zum Überprüfen des in das Dialogfeld.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CColorDialog::m\_cc](../Topic/CColorDialog::m_cc.md)|Eine Struktur verwendet, um die Einstellungen des Dialogfelds anzupassen.|  
  
## Hinweise  
 Ein Objekt `CColorDialog` ist ein Dialogfeld mit einer Liste von Farben, die für das Anzeigesystem definiert werden.  Der Benutzer kann eine bestimmte Farbe aus der Liste auswählen oder erstellen, die dann an die Anwendung ausgegeben wird, wenn das Dialogfeld beendet.  
  
 So fügen Sie ein `CColorDialog`\-Objekt erstellen, den bereitgestellten Konstruktor verwenden oder eine neue Klasse ableiten und den eigenen benutzerdefinierten Konstruktor verwenden.  
  
 Wenn das Dialogfeld erstellt wurde, können Sie alle Werte in der [m\_cc](../Topic/CColorDialog::m_cc.md)\-Struktur festlegen oder ändern, um die Werte der Steuerelemente des Dialogfelds zu initialisieren.  Die `m_cc`\-Struktur ist vom Typ [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 Nachdem Sie die Steuerelemente des Dialogfelds initialisiert haben, rufen Sie die `DoModal`\-Memberfunktion auf, um das Dialogfeld anzuzeigen und dem Benutzer zu ermöglichen, eine Farbe auszuwählen.  `DoModal` gibt die Auswahl des Benutzers entweder OK des Dialogfelds \(**IDOK**\) oder von Schaltfläche Löschverhalten \(**IDCANCEL**\) zurück.  
  
 Wenn `DoModal`**IDOK** zurückgibt, können Sie eine der Memberfunktionen von `CColorDialog` verwenden, um die Informationseingabe durch den Benutzer abzurufen.  
  
 Sie können die Funktion Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) verwenden, um mehr über den Fehler zu ermitteln, ob ein Fehler aufgetreten ist während der Initialisierung des Dialogfelds und zu erfahren.  
  
 `CColorDialog` beruht auf der COMMDLG.DLL\-Datei, die mit Windows\-Versionen 3,1 und höher bereitgestellt wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CColorDialog`, erstellen Sie eine benutzerdefinierte Dialogfeldvorlage, und fügen Sie eine Meldungszuordnung hinzu um die Benachrichtigungsmeldungen aus den erweiterten \- Steuerelementen verarbeiten.  Alle nicht verarbeiteten Nachrichten sollten die Basisklasse übergeben werden.  
  
 Die Hookfunktion anzupassen ist nicht erforderlich.  
  
> [!NOTE]
>  Bei einigen Installationen wird das `CColorDialog`\-Objekt nicht mit einem grauen Hintergrund angezeigt, wenn Sie das Framework verwendet haben, um andere `CDialog`\-Objektgrau auszuführen.  
  
 Weitere Informationen zur Verwendung von `CColorDialog`, finden Sie unter [Allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md)  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [MFC Sampling MDI](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DRAWCLI](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)