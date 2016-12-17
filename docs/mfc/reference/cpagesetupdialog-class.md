---
title: "CPageSetupDialog Class"
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
  - "CPageSetupDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPageSetupDialog class"
  - "OLE Page Setup dialog box"
  - "Seite einrichten"
  - "Seite einrichten (Dialogfeld)"
  - "Print Setup dialog box"
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CPageSetupDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Dienste, die durch das allgemeine OLE Seiteneinrichtungsdialogfeld Windows mit zusätzliche Unterstützung für das Festlegen und Ändern von Drucksrändern bereitgestellt werden.  
  
## Syntax  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](../Topic/CPageSetupDialog::CPageSetupDialog.md)|Erstellt ein `CPageSetupDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](../Topic/CPageSetupDialog::CreatePrinterDC.md)|Erstellt einen Gerätekontext für das Drucken.|  
|[CPageSetupDialog::DoModal](../Topic/CPageSetupDialog::DoModal.md)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer machen eine Auswahl.|  
|[CPageSetupDialog::GetDeviceName](../Topic/CPageSetupDialog::GetDeviceName.md)|Gibt den Gerätenamen des Druckers zurück.|  
|[CPageSetupDialog::GetDevMode](../Topic/CPageSetupDialog::GetDevMode.md)|Gibt aktuelle `DEVMODE` des Druckers zurück.|  
|[CPageSetupDialog::GetDriverName](../Topic/CPageSetupDialog::GetDriverName.md)|Gibt den Treiber zurück, der vom Drucker verwendet wird.|  
|[CPageSetupDialog::GetMargins](../Topic/CPageSetupDialog::GetMargins.md)|Gibt die aktuellen Seitenrandeinstellungen des Druckers zurück.|  
|[CPageSetupDialog::GetPaperSize](../Topic/CPageSetupDialog::GetPaperSize.md)|Gibt das Papierformat des Druckers zurück.|  
|[CPageSetupDialog::GetPortName](../Topic/CPageSetupDialog::GetPortName.md)|Gibt den Ausgabeanschlussnamen zurück.|  
|[CPageSetupDialog::OnDrawPage](../Topic/CPageSetupDialog::OnDrawPage.md)|Aufgerufen durch das Framework, um eine Bildschirmaufnahme einer gedruckten Seite zu rendern.|  
|[CPageSetupDialog::PreDrawPage](../Topic/CPageSetupDialog::PreDrawPage.md)|Aufgerufen vom Framework, bevor eine Bildschirmaufnahme einer gedruckten Seite gerendert wird.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPageSetupDialog::m\_psd](../Topic/CPageSetupDialog::m_psd.md)|Eine Struktur verwendet, um ein `CPageSetupDialog`\-Objekt anzupassen.|  
  
## Hinweise  
 Diese Klasse wurde entwickelt, um des Drucks\-Setupdialogfelds erfolgen.  
  
 Um ein `CPageSetupDialog`\-Objekt zu verwenden, erstellen Sie zunächst das Objekt mithilfe des `CPageSetupDialog`\-Konstruktors.  Wenn das Dialogfeld erstellt wurde, können Sie alle Werte im `m_psd` Datenmember festlegen oder ändern, um die Werte der Steuerelemente des Dialogfelds zu initialisieren.  Die [m\_psd](../Topic/CPageSetupDialog::m_psd.md)\-Struktur ist vom Typ **PAGESETUPDLG**.  
  
 Nachdem Sie die Dialogfeld\-Steuerelemente initialisiert haben, rufen Sie die `DoModal`\-Memberfunktion auf, um das Dialogfeld anzuzeigen und den Benutzer zu den ausgewählten Druckoptionen zu ermöglichen.  `DoModal` gibt zurück, ob der Benutzer OK \(**IDOK**\) oder Schaltfläche Löschverhalten \(**IDCANCEL**\) ausgewählt hat.  
  
 Wenn `DoModal`**IDOK** zurückgibt, können Sie mehrere Memberfunktionen von `CPageSetupDialog` verwenden, oder können Sie im `m_psd` Datenmember an, um Informationseingabe durch den Benutzer abzurufen.  
  
> [!NOTE]
>  Nachdem das Common OLE Seiteneinrichtungsdialogfeld geschlossen ist, werden keine Änderungen, die vom Benutzer vorgenommen werden, nicht durch das Framework gespeichert.  Es ist bis zur Anwendung selbst, alle Werte dieses Dialogfeld in einen permanenten Speicherort, wie der Member des Dokuments oder der Anwendungsklasse Anwendung zu speichern.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [MFC\-Beispiel WORDPAD](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)