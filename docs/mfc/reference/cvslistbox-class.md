---
title: "CVSListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CVSListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVSListBox class"
  - "CVSListBox::PreTranslateMessage method"
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CVSListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CVSListBox`\-Klasse unterstützt ein bearbeitbares Listensteuerelement.  
  
## Syntax  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](../Topic/CVSListBox::CVSListBox.md)|Erstellt ein `CVSListBox`\-Objekt.|  
|`CVSListBox::~CVSListBox`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CVSListBox::AddItem](../Topic/CVSListBox::AddItem.md)|Fügt eine Zeichenfolge einem Listensteuerelement hinzu.  \(Überschreibungen `CVSListBoxBase::AddItem`.\)|  
|[CVSListBox::EditItem](../Topic/CVSListBox::EditItem.md)|Startet einen Bearbeitungsvorgang im Text eines Listensteuerelementelements.  \(Überschreibungen `CVSListBoxBase::EditItem`.\)|  
|[CVSListBox::GetCount](../Topic/CVSListBox::GetCount.md)|Ruft die Anzahl der Zeichenfolgen in einem bearbeitbaren Listensteuerelement ab.  \(Überschreibungen `CVSListBoxBase::GetCount`.\)|  
|[CVSListBox::GetItemData](../Topic/CVSListBox::GetItemData.md)|Ruft einen anwendungsspezifischen 32\-Bit\-Wert ab, der mit einem bearbeitbaren Listensteuerelementelement zugeordnet ist.  \(Überschreibungen `CVSListBoxBase::GetItemData`.\)|  
|[CVSListBox::GetItemText](../Topic/CVSListBox::GetItemText.md)|Ruft den Text eines bearbeitbaren Listensteuerelementelements ab.  \(Überschreibungen `CVSListBoxBase::GetItemText`.\)|  
|[CVSListBox::GetSelItem](../Topic/CVSListBox::GetSelItem.md)|Ruft den nullbasierten Index des aktuell ausgewählten Elements in einem bearbeitbaren Listensteuerelement ab.  \(Überschreibungen `CVSListBoxBase::GetSelItem`.\)|  
|`CVSListBox::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  Weitere Informationen und Methodensyntax finden Sie unter [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Überschreibungen `CVSListBoxBase::PreTranslateMessage`.\)|  
|[CVSListBox::RemoveItem](../Topic/CVSListBox::RemoveItem.md)|Entfernt ein Element aus einem bearbeitbaren Listensteuerelement.  \(Überschreibungen `CVSListBoxBase::RemoveItem`.\)|  
|[CVSListBox::SelectItem](../Topic/CVSListBox::SelectItem.md)|Wählt eine bearbeitbare Listensteuerelementzeichenfolge aus.  \(Überschreibungen `CVSListBoxBase::SelectItem`.\)|  
|[CVSListBox::SetItemData](../Topic/CVSListBox::SetItemData.md)|Ordnet einen anwendungsspezifischen 32\-Bit\-Wert mit einem bearbeitbaren Listensteuerelementelement zu.  \(Überschreibungen `CVSListBoxBase::SetItemData`.\)|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](../Topic/CVSListBox::GetListHwnd.md)|Gibt das Handle zur aktuellen eingebetteten Listenansicht\-Steuerelement zurück.|  
  
## Hinweise  
 Die Klasse stellt einen Satz `CVSListBox` Bearbeitungsschaltflächen, die den Benutzern ermöglichen, die Elemente in einem Listensteuerelement zu erstellen, zu ändern, zu löschen oder neu anzuordnen.  
  
 Im Folgenden ist ein Bild des bearbeitbaren Listensteuerelements.  Der zweite Listeneintrag, der "Element2" So, wird für Bearbeitung ausgewählt.  
  
 ![CVSListBox&#45;Steuerelement](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 Wenn Sie den Ressourcen\-Editor verwenden, um ein bearbeitbares Listensteuerelement hinzuzufügen, Sie, dass der Bereich **Werkzeugkasten** des Editors kein vordefiniertes bearbeitbares Listensteuerelement bereitstellt.  Stattdessen fügen Sie ein statisches Steuerelement wie das Steuerelement **Gruppenfeld** hinzu.  Das Framework verwendet das statische Steuerelement als Platzhalter, die Größe und Position des bearbeitbaren Listensteuerelements anzugeben.  
  
 Um ein bearbeitbares Listensteuerelement in einer Dialogfeldvorlage zu verwenden, deklarieren Sie eine Variable `CVSListBox` in der Dialogfeldklasse.  Um Datenaustausch zwischen der Variablen und dem Steuerelement zu unterstützen, definieren Sie einen `DDX_Control`\-Makroeintrag in der `DoDataExchange`\-Methode des Dialogfelds.  Standardmäßig wird das bearbeitbare Listensteuerelement ohne Bearbeitungsschaltflächen erstellt.  Verwenden Sie die [CVSListBoxBase::SetStandardButtons](assetId:///129e530f-97e9-42eb-b128-371c2a5686ba) geerbte Methode, um die Bearbeitungsschaltflächen zu aktivieren.  
  
 Weitere Informationen finden Sie im Beispielverzeichnis, das `New Controls` Beispiel, die Page3.cpp\- und Page3.h\-Dateien.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## Anforderungen  
 **Header:** afxvslistbox.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)