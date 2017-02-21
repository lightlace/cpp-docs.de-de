---
title: "CMFCToolBarsCustomizeDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarsCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarsCustomizeDialog class"
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCToolBarsCustomizeDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein nicht modales Dialogfeld im Registerformat \([CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)\) das dem Benutzer ermöglicht, die Symbolleisten, die Menüs, die Tastenkombinationen, die benutzerdefinierten Tools und den visuellen Stil in einer Anwendung anzupassen.  In der Regel die auf dieses Dialogfeld durch Auswählen von **Anpassen** vom Menü **Tools**.  
  
 Das Dialogfeld **Anpassen** verfügt über sechs Registerkarten: **Befehle**, **Symbolleisten**, **Tools**, **Tastatur**, **Menü** und **Optionen**.  
  
## Syntax  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](../Topic/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog.md)|Erstellt ein `CMFCToolBarsCustomizeDialog`\-Objekt.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md)|Fügt eine Symbolleisten\-Schaltfläche in die Liste von Befehlen auf der Seite ein **Befehle**|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](../Topic/CMFCToolBarsCustomizeDialog::AddMenu.md)|Lädt ein Menü von Ressourcen und [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) ruft auf, um das Menü der Liste von Befehlen auf der Seite **Befehle** hinzuzufügen.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md)|Lädt ein Menü von Ressourcen und [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) ruft auf, um das Menü der Liste von Befehlen auf der Seite **Befehle** hinzuzufügen.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](../Topic/CMFCToolBarsCustomizeDialog::AddToolBar.md)|Lädt eine Symbolleiste von Ressourcen.  Anschließend denn jeder Befehl im Menü [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md) ruft die Methode auf, um eine Schaltfläche in der Liste von Befehlen **Befehle** auf der Seite unter die angegebene Kategorie einzufügen.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)|Zeigt das Dialogfeld an. **Anpassung**|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Für die zukünftige Verwendung reserviert.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](../Topic/CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars.md)|Aktiviert oder deaktiviert das Erstellen neuer Symbolleisten mithilfe des Dialogfelds **Anpassen**.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](../Topic/CMFCToolBarsCustomizeDialog::FillAllCommandsList.md)|Füllt das bereitgestellte Objekt `CListBox` mit den Befehlen in der Kategorie **Alle Befehle** auf.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox.md)|Füllt das bereitgestellte `CComboBox`\-Objekt mit dem Namen jeder Befehlskategorie **Anpassen** im Dialogfeld auf.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesListBox.md)|Füllt das bereitgestellte `CListBox`\-Objekt mit dem Namen jeder Befehlskategorie **Anpassen** im Dialogfeld auf.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](../Topic/CMFCToolBarsCustomizeDialog::GetCommandName.md)|Ruft den Namen ab, der der angegebenen Befehl ID zugeordnet ist|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](../Topic/CMFCToolBarsCustomizeDialog::GetCountInCategory.md)|Ruft die Anzahl der Elemente in der Liste ab, die eine angegebene Beschriftung haben.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](../Topic/CMFCToolBarsCustomizeDialog::GetFlags.md)|Ruft den Satz von Flags ab, die das Verhalten des Dialogfelds auswirken.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](../Topic/CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage.md)|Startet eine Bildbearbeitung, sodass ein Benutzer ein Symbolleistenschaltflächen\- oder Menüelementsymbol anpassen kann.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](../Topic/CMFCToolBarsCustomizeDialog::OnInitDialog.md)|überschreibt, um von Eigenschaftenblattinitialisierung zu erweitern.  \(Überschreibungen [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md).\)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](../Topic/CMFCToolBarsCustomizeDialog::PostNcDestroy.md)|Aufgerufen vom Framework, nachdem das Fenster zerstört wurde.  \(Überschreibungen `CPropertySheet::PostNcDestroy`.\)|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](../Topic/CMFCToolBarsCustomizeDialog::RemoveButton.md)|Entfernt die Schaltfläche mit der angegebenen Befehls\-ID aus der angegebenen Kategorie oder aller Kategorien.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](../Topic/CMFCToolBarsCustomizeDialog::RenameCategory.md)|Benennt eine Kategorie im Listenfeld der Kategorien auf der Registerkarte **Befehle**.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)|Ersetzt eine Schaltfläche in der Liste von Befehlen auf der Registerkarte **Befehle** durch ein neues Symbolleistenschaltflächenobjekt.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](../Topic/CMFCToolBarsCustomizeDialog::SetUserCategory.md)|Fügt eine Kategorie der Liste der Kategorien hinzu, die auf der Registerkarte **Befehle** angezeigt werden.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](../Topic/CMFCToolBarsCustomizeDialog::CheckToolsValidity.md)|Aufgerufen vom Framework, um zu bestimmen, ob die Liste von benutzerdefinierten Tools gültig ist.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnAfterChangeTool.md)|Aufgerufen vom Framework wenn die Eigenschaften einer benutzerdefinierten Tooländerung.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](../Topic/CMFCToolBarsCustomizeDialog::OnAssignKey.md)|Bestimmt, ob eine angegebene Zugriffstaste zu einer Aktion zugewiesen werden kann.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnBeforeChangeTool.md)|Bestimmt, ob ein benutzerdefiniertes Tool geändert werden kann.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](../Topic/CMFCToolBarsCustomizeDialog::OnInitToolsPage.md)|Aufgerufen vom Framework, wenn der Benutzer auswählt, wird die Registerkarte **Tools** angefordert.|  
  
## Hinweise  
 Um das Dialogfeld **Anpassen** anzuzeigen, erstellen Sie ein `CMFCToolBarsCustomizeDialog`\-Objekt und rufen Sie die [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)\-Methode auf.  
  
 Während das Dialogfeld **Anpassen** aktiv ist, wird die Anwendung in einem bestimmten Modus, der der Benutzer den Anpassungsaufgaben beschränkt.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCToolBarsCustomizeDialog` verwendet.  Im Beispiel wird gezeigt, wie eine Symbolleistenschaltfläche im Listenfeld von Befehlen auf der Seite **Befehle**, ermöglichen das Erstellen neuer Symbolleisten, indem das Dialogfeld **Anpassen** verwenden, und das Dialogfeld anzeigen **Anpassung** ersetzt.  Dieser Codeausschnitt ist Teil [IE\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_IEDemo#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_IEDemo#4)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)  
  
## Anforderungen  
 **Header:** afxToolBarsCustomizeDialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)