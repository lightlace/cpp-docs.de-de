---
title: "CMFCKeyMapDialog Class"
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
  - "CMFCKeyMapDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCKeyMapDialog class"
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCKeyMapDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCKeyMapDialog`\-Klasse unterstützt ein Steuerelement, das Befehle auf Schlüssel auf der Tastatur zuordnet.  
  
## Syntax  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](../Topic/CMFCKeyMapDialog::CMFCKeyMapDialog.md)|Erstellt ein `CMFCKeyMapDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](../Topic/CMFCKeyMapDialog::DoModal.md)|Zeigt ein Tastaturzuordnungsschemadialogfeld an.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](../Topic/CMFCKeyMapDialog::FormatItem.md)|Aufgerufen vom Framework, um eine Zeichenfolge zu erstellen, die eine Tastenzuordnung beschreibt.  Standardmäßig enthält die Zeichenfolge den Befehlsnamen, die verwendeten Tastenkombinationen und die Tastenkombinationsbeschreibung.|  
|[CMFCKeyMapDialog::GetCommandKeys](../Topic/CMFCKeyMapDialog::GetCommandKeys.md)|Ruft eine Zeichenfolge ab, die eine Liste der Tastenkombinationen enthält, die dem angegebenen Befehl zugeordnet sind.|  
|[CMFCKeyMapDialog::OnInsertItem](../Topic/CMFCKeyMapDialog::OnInsertItem.md)|Aufgerufen vom Framework, bevor ein neues Element in das interne Listensteuerelement eingefügt wird, das das Tastaturzuordnungsschemasteuerelement unterstützt.|  
|[CMFCKeyMapDialog::OnPrintHeader](../Topic/CMFCKeyMapDialog::OnPrintHeader.md)|Aufgerufen vom Framework, um den Header für die Tastaturzuordnung auf einer neuen Seite auszugeben.|  
|[CMFCKeyMapDialog::OnPrintItem](../Topic/CMFCKeyMapDialog::OnPrintItem.md)|Aufgerufen vom Framework, um ein Tastaturzuordnungsschemaelement auszugeben.|  
|[CMFCKeyMapDialog::OnSetColumns](../Topic/CMFCKeyMapDialog::OnSetColumns.md)|Aufgerufen durch das Framework, um Beschriftungen für die Spalten im internen Listensteuerelement festzulegen, das das Tastaturzuordnungsschemasteuerelement unterstützt.|  
|[CMFCKeyMapDialog::PrintKeyMap](../Topic/CMFCKeyMapDialog::PrintKeyMap.md)|Aufgerufen vom Framework ausgelöst, wenn ein Benutzer auf die Schaltfläche klickt. **Drucken**|  
|[CMFCKeyMapDialog::SetColumnsWidth](../Topic/CMFCKeyMapDialog::SetColumnsWidth.md)|Aufgerufen durch das Framework, um die Breite der Spalten im internen Listensteuerelement festzulegen, das das Tastaturzuordnungsschemasteuerelement unterstützt.|  
  
## Hinweise  
 Verwenden Sie die `CMFCKeyMapDialog`\-Klasse, um ein in der Größe veränderbares Tastaturzuordnungsschemadialogfeld zu implementieren.  Das Dialogfeld wird ein ListView\-Steuerelement, um Zugriffstasten und ihre zugeordneten Befehle anzuzeigen.  
  
 Um die `CMFCKeyMapDialog`\-Klasse in einer Anwendung zu verwenden, übergeben Sie einen Zeiger auf das Hauptrahmenfenster als Parameter an den `CMFCKeyMapDialog`\-Konstruktor.  Rufen Sie dann die `DoModal`\-Methode, um ein modales Dialogfeld zu starten.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## Anforderungen  
 **Header:** afxkeymapdialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)