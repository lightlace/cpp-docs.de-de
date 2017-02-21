---
title: "CPrintDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialog class"
  - "Drucken (Dialogfeld)"
  - "Print Setup dialog box"
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CPrintDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Dienste, die vom Windows\-häufigverwendetes Dialogfeld für das Drucken bereitgestellt werden.  
  
## Syntax  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](../Topic/CPrintDialog::CPrintDialog.md)|Erstellt ein `CPrintDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](../Topic/CPrintDialog::CreatePrinterDC.md)|Erstellt einen Druckergerätekontext, ohne das Dialogfeld Drucken anzuzeigen.|  
|[CPrintDialog::DoModal](../Topic/CPrintDialog::DoModal.md)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer, um die Auswahl zu machen.|  
|[CPrintDialog::GetCopies](../Topic/CPrintDialog::GetCopies.md)|Ruft die Anzahl der angeforderten Kopien ab.|  
|[CPrintDialog::GetDefaults](../Topic/CPrintDialog::GetDefaults.md)|Ruft Gerätenstandards ab, ohne ein Dialogfeld anzuzeigen.|  
|[CPrintDialog::GetDeviceName](../Topic/CPrintDialog::GetDeviceName.md)|Ruft den Namen des Geräts des derzeit ausgewählten Druckers ab.|  
|[CPrintDialog::GetDevMode](../Topic/CPrintDialog::GetDevMode.md)|Ruft die `DEVMODE`\-Struktur ab.|  
|[CPrintDialog::GetDriverName](../Topic/CPrintDialog::GetDriverName.md)|Ruft den Namen des Treibers des derzeit ausgewählten Druckers ab.|  
|[CPrintDialog::GetFromPage](../Topic/CPrintDialog::GetFromPage.md)|Ruft die Startseite des Drucksbereichs ab.|  
|[CPrintDialog::GetPortName](../Topic/CPrintDialog::GetPortName.md)|Ruft den Namen des aktuell Ports des ausgewählten Druckers ab.|  
|[CPrintDialog::GetPrinterDC](../Topic/CPrintDialog::GetPrinterDC.md)|Ruft ein Handle für Druckergerätekontext ab.|  
|[CPrintDialog::GetToPage](../Topic/CPrintDialog::GetToPage.md)|Ruft die Endeseite des Drucksbereichs ab.|  
|[CPrintDialog::PrintAll](../Topic/CPrintDialog::PrintAll.md)|Bestimmt, ob alle Seiten des Dokuments gedruckt wird.|  
|[CPrintDialog::PrintCollate](../Topic/CPrintDialog::PrintCollate.md)|Bestimmt, ob sortierte Kopien angefordert werden.|  
|[CPrintDialog::PrintRange](../Topic/CPrintDialog::PrintRange.md)|Bestimmt, ob nur einen bestimmten Seitenbereich ausgibt.|  
|[CPrintDialog::PrintSelection](../Topic/CPrintDialog::PrintSelection.md)|Bestimmt, ob nur die aktuell ausgewählten Elemente ausgibt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintDialog::m\_pd](../Topic/CPrintDialog::m_pd.md)|Eine Struktur verwendet, um ein `CPrintDialog`\-Objekt anzupassen.|  
  
## Hinweise  
 Allgemeine Druckdialogfeldfelder bieten eine einfache Möglichkeit, die Drucks\- und Drucks\-Setupdialogfelder zu implementieren, die mit Windows\-Standards in ähnlicher Weise konsistent sind.  
  
> [!NOTE]
>  Die `CPrintDialogEx`\-Klasse kapselt die Dienste, die vom Windows 2000druckseigenschaftenblatt bereitgestellt werden.  Weitere Informationen finden Sie in [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) Übersicht.  
  
 Die Funktionalität von `CPrintDialog` wird durch die von [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md) ersetzt, die entwickelt wurde, um Sie mit einem Standarddialogfelder für Druckssetup und \-Seiteneinrichtung bereitzustellen.  
  
 Sie können auf das Framework verlassen, um viele Aspekte des Druckvorgangs für die Anwendung zu behandeln.  In diesem Fall zeigt das Framework automatisch das Dialogfeld Windows\-häufigverwendetes für das Drucken an.  Sie können den Frameworkhandledruck für die Anwendung verfügen jedoch das Standarddialogfeld Drucken mit Ihrem eigenen Dialogfeld Drucken überschreiben.  Weitere Informationen zum Verwenden des Frameworks, um Drucksaufgaben zu behandeln, finden Sie im Artikel [Drucken](../../mfc/printing.md).  
  
 Wenn Sie die Anwendung soll, Drucken ohne die Beteiligung des Frameworks zu behandeln, können Sie die Klasse verwenden `CPrintDialog` "z" mit dem bereitgestellten Konstruktor ist, oder eine eigene Dialogfeldklasse von `CPrintDialog` ableiten und einen Konstruktor schreiben, um Ihre Anforderungen anpassen.  In beiden Fällen verhalten sich diese Dialogfelder wie Standard\-MFC\-Dialogfelder, da sie von der Klasse `CCommonDialog` abgeleitet werden.  
  
 Um ein `CPrintDialog`\-Objekt zu verwenden, erstellen Sie zunächst das Objekt mithilfe des `CPrintDialog`\-Konstruktors.  Wenn das Dialogfeld erstellt wurde, können Sie alle Werte in der [m\_pd](../Topic/CPrintDialog::m_pd.md)\-Struktur festlegen oder ändern, um die Werte der Steuerelemente des Dialogfelds zu initialisieren.  Die `m_pd`\-Struktur ist vom Typ [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843).  Weitere Informationen über diese Struktur, finden Sie unter [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn Sie keine eigenen Handles in `m_pd` für die **hDevMode** und **hDevNames**\-Member angeben, stellen Sie sicher, die Windows\-Funktion **GlobalFree** für diese Handles aufrufen, wenn Sie mit dem Dialogfeld geschehen.  Wenn Sie die der Drucks\-Setupimplementierung des Frameworks verwenden, die von `CWinApp::OnFilePrintSetup` bereitgestellt wird, müssen Sie diese Handles nicht freigeben.  Die Handles werden durch `CWinApp` verwaltet und werden im Destruktor von `CWinApp` freigegeben.  Es ist nur erforderlich, diese Handles freizugeben, wenn ein eigenständiges `CPrintDialog` verwendet.  
  
 Nachdem Sie die Dialogfeld\-Steuerelemente initialisiert haben, rufen Sie die `DoModal`\-Memberfunktion auf, um das Dialogfeld anzuzeigen und den Benutzer zu den ausgewählten Druckoptionen zu ermöglichen.  `DoModal` gibt zurück, ob der Benutzer OK \(**IDOK**\) oder Schaltfläche Löschverhalten \(**IDCANCEL**\) ausgewählt hat.  
  
 Wenn `DoModal`**IDOK** zurückgibt, können Sie eine der Memberfunktionen von `CPrintDialog` verwenden, um die Informationseingabe durch den Benutzer abzurufen.  
  
 Die `CPrintDialog::GetDefaults`\-Memberfunktion ist für das Abrufen der aktuellen Druckerstandards nützlich, ohne ein Dialogfeld anzuzeigen.  Diese Memberfunktion ist keine Benutzerinteraktion.  
  
 Sie können die Funktion Windows **CommDlgExtendedError** verwenden, um mehr über den Fehler zu ermitteln, ob ein Fehler aufgetreten ist während der Initialisierung des Dialogfelds und zu erfahren.  Weitere Informationen zu dieser Funktion finden Sie unter, [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CPrintDialog` beruht auf der COMMDLG.DLL\-Datei, die mit Windows\-Versionen 3,1 und höher bereitgestellt wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CPrintDialog`, erstellen Sie eine benutzerdefinierte Dialogfeldvorlage, und fügen Sie eine Meldungszuordnung hinzu um die Benachrichtigungsmeldungen aus den erweiterten \- Steuerelementen verarbeiten.  Alle nicht verarbeiteten Nachrichten sollten die Basisklasse an übergeben werden.  Die Hookfunktion anzupassen ist nicht erforderlich.  
  
 Um die gleiche Meldung abhängig von unterschiedlich zu verarbeiten oder ob das Dialogfeld Drucken Drucks\-Setup ist, müssen Sie eine Klasse für jedes Dialogfeld berechnen.  Sie müssen die Funktion Windows **AttachOnSetup** auch überschreiben, die die Erstellung eines neuen Dialogfelds behandelt, wenn die Drucks\-Setupschaltfläche innerhalb eines Druckdialogfeldfelds ausgewählt ist.  
  
 Weitere Informationen zur Verwendung von `CPrintDialog`, finden Sie unter [Allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [MFC Sampling DIBLOOK](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)