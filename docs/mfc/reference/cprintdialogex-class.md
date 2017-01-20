---
title: "CPrintDialogEx Class"
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
  - "CPrintDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialogEx class"
  - "Drucken (Dialogfeld)"
  - "Print Setup dialog box"
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Dienste, die vom Windows 2000druckseigenschaftenblatt bereitgestellt werden.  
  
## Syntax  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](../Topic/CPrintDialogEx::CPrintDialogEx.md)|Erstellt ein `CPrintDialogEx`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](../Topic/CPrintDialogEx::CreatePrinterDC.md)|Erstellt einen Druckergerätekontext, ohne das Dialogfeld Drucken anzuzeigen.|  
|[CPrintDialogEx::DoModal](../Topic/CPrintDialogEx::DoModal.md)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer, um auswählen kann.|  
|[CPrintDialogEx::GetCopies](../Topic/CPrintDialogEx::GetCopies.md)|Ruft die Anzahl der angeforderten Kopien ab.|  
|[CPrintDialogEx::GetDefaults](../Topic/CPrintDialogEx::GetDefaults.md)|Ruft Gerätenstandards ab, ohne ein Dialogfeld anzuzeigen.|  
|[CPrintDialogEx::GetDeviceName](../Topic/CPrintDialogEx::GetDeviceName.md)|Ruft den Namen des Geräts des derzeit ausgewählten Druckers ab.|  
|[CPrintDialogEx::GetDevMode](../Topic/CPrintDialogEx::GetDevMode.md)|Ruft die `DEVMODE`\-Struktur ab.|  
|[CPrintDialogEx::GetDriverName](../Topic/CPrintDialogEx::GetDriverName.md)|Ruft den Namen des systemdefinierten Druckergerätetreibers ab.|  
|[CPrintDialogEx::GetPortName](../Topic/CPrintDialogEx::GetPortName.md)|Ruft den Namen des aktuell Ports des ausgewählten Druckers ab.|  
|[CPrintDialogEx::GetPrinterDC](../Topic/CPrintDialogEx::GetPrinterDC.md)|Ruft ein Handle für Druckergerätekontext ab.|  
|[CPrintDialogEx::PrintAll](../Topic/CPrintDialogEx::PrintAll.md)|Bestimmt, ob alle Seiten des Dokuments gedruckt wird.|  
|[CPrintDialogEx::PrintCollate](../Topic/CPrintDialogEx::PrintCollate.md)|Bestimmt, ob sortierte Kopien angefordert werden.|  
|[CPrintDialogEx::PrintCurrentPage](../Topic/CPrintDialogEx::PrintCurrentPage.md)|Bestimmt, ob die aktuelle Seite des Dokuments gedruckt wird.|  
|[CPrintDialogEx::PrintRange](../Topic/CPrintDialogEx::PrintRange.md)|Bestimmt, ob nur einen bestimmten Seitenbereich ausgibt.|  
|[CPrintDialogEx::PrintSelection](../Topic/CPrintDialogEx::PrintSelection.md)|Bestimmt, ob nur die aktuell ausgewählten Elemente ausgibt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintDialogEx::m\_pdex](../Topic/CPrintDialogEx::m_pdex.md)|Eine Struktur verwendet, um ein `CPrintDialogEx`\-Objekt anzupassen.|  
  
## Hinweise  
 Sie können auf das Framework verlassen, um viele Aspekte des Druckvorgangs für die Anwendung zu behandeln.  Weitere Informationen zum Verwenden des Frameworks, um Drucksaufgaben zu behandeln, finden Sie im Artikel [Drucken](../../mfc/printing.md).  
  
 Wenn Sie die Anwendung soll, Drucken ohne die Beteiligung des Frameworks zu behandeln, können Sie die Klasse verwenden `CPrintDialogEx` "z" mit dem bereitgestellten Konstruktor ist, oder eine eigene Dialogfeldklasse von `CPrintDialogEx` ableiten und einen Konstruktor schreiben, um Ihre Anforderungen anpassen.  In beiden Fällen verhalten sich diese Dialogfelder wie Standard\-MFC\-Dialogfelder, da sie von der Klasse `CCommonDialog` abgeleitet werden.  
  
 Um ein `CPrintDialogEx`\-Objekt zu verwenden, erstellen Sie zunächst das Objekt mithilfe des `CPrintDialogEx`\-Konstruktors.  Wenn das Dialogfeld erstellt wurde, können Sie alle Werte in der [m\_pdex](../Topic/CPrintDialogEx::m_pdex.md)\-Struktur festlegen oder ändern, um die Werte der Steuerelemente des Dialogfelds zu initialisieren.  Die `m_pdex`\-Struktur ist vom Typ [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844).  Weitere Informationen über diese Struktur, finden Sie unter [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn Sie keine eigenen Handles in `m_pdex` für die **hDevMode** und **hDevNames**\-Member angeben, stellen Sie sicher, die Windows\-Funktion **GlobalFree** für diese Handles aufrufen, wenn Sie mit dem Dialogfeld geschehen.  
  
 Nachdem Sie die Dialogfeld\-Steuerelemente initialisiert haben, rufen Sie die `DoModal`\-Memberfunktion auf, um das Dialogfeld anzuzeigen und den Benutzer zu den ausgewählten Druckoptionen zu ermöglichen.  Wenn `DoModal` zurückgibt, können Sie bestimmen, ob der Benutzer OK ausgewählt hat, wendet oder Schaltfläche abgebrochen wird.  
  
 Wenn der Benutzer auf OK geklickt hat, können Sie die Memberfunktionen von `CPrintDialogEx` verwenden, um die Informationseingabe durch den Benutzer abzurufen.  
  
 Die `CPrintDialogEx::GetDefaults`\-Memberfunktion ist für das Abrufen der aktuellen Druckerstandards nützlich, ohne ein Dialogfeld anzuzeigen.  Diese Methode erfordert keine Benutzerinteraktion.  
  
 Sie können die Funktion Windows **CommDlgExtendedError** verwenden, um mehr über den Fehler zu ermitteln, ob ein Fehler aufgetreten ist während der Initialisierung des Dialogfelds und zu erfahren.  Weitere Informationen zu dieser Funktion finden Sie unter, [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zur Verwendung von `CPrintDialogEx`, finden Sie unter [Allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)