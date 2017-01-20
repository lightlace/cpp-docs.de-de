---
title: "CComboBoxEx Class"
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
  - "CComboBoxEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBoxEx class"
  - "Kombinationsfelder [C++], CComboBoxEx class"
  - "common controls [C++], extended combo boxes"
  - "extended combo boxes, CComboBoxEx class"
  - "Internet Explorer 4.0 common controls"
  - "Windows common controls [C++], extended combo boxes"
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CComboBoxEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erweitert das Kombinationsfeld\-Steuerelement durch die Unterstützung Bildlisten.  
  
## Syntax  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComboBoxEx::CComboBoxEx](../Topic/CComboBoxEx::CComboBoxEx.md)|Erstellt ein `CComboBoxEx`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComboBoxEx::Create](../Topic/CComboBoxEx::Create.md)|Stellt das Kombinationsfeld erstellt und fügt es an den `CComboBoxEx`\-Objekt.|  
|[CComboBoxEx::CreateEx](../Topic/CComboBoxEx::CreateEx.md)|Stellt ein Kombinationsfeld mit den angegebenen Windows\-erweitertenFormaten erstellt und am **ComboBoxEx** einem Objekt an.|  
|[CComboBoxEx::DeleteItem](../Topic/CComboBoxEx::DeleteItem.md)|Entfernt ein Element aus einem **ComboBoxEx**\-Steuerelement.|  
|[CComboBoxEx::GetComboBoxCtrl](../Topic/CComboBoxEx::GetComboBoxCtrl.md)|Ruft einen Zeiger auf den untergeordneten Kombinationsfeld\-Steuerelement ab.|  
|[CComboBoxEx::GetEditCtrl](../Topic/CComboBoxEx::GetEditCtrl.md)|Ruft das Handle für Bearbeitungssteuerelementteil **ComboBoxEx** eines Steuerelements ab.|  
|[CComboBoxEx::GetExtendedStyle](../Topic/CComboBoxEx::GetExtendedStyle.md)|Ruft die erweiterten Stile ab, die für ein **ComboBoxEx**\-Steuerelement verwendet werden.|  
|[CComboBoxEx::GetImageList](../Topic/CComboBoxEx::GetImageList.md)|Ruft einen Zeiger auf die Bildliste ab, die einem **ComboBoxEx**\-Steuerelement zugewiesen wird.|  
|[CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md)|Ruft **ComboBoxEx**\-Elementinformationen für ein angegebenes Element ab.|  
|[CComboBoxEx::HasEditChanged](../Topic/CComboBoxEx::HasEditChanged.md)|Bestimmt, ob der Benutzer den Inhalt des Bearbeitungssteuerelements **ComboBoxEx** geändert wurde, indem Sie eingegeben hat.|  
|[CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md)|Fügt ein neues Element in einem **ComboBoxEx**\-Steuerelement ein.|  
|[CComboBoxEx::SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)|Legt erweiterte Formate **ComboBoxEx** innerhalb eines \- Steuerelements fest.|  
|[CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md)|Legt eine Bildliste für ein **ComboBoxEx**\-Steuerelement fest.|  
|[CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md)|Legt die Attribute für ein Element in einem **ComboBoxEx**\-Steuerelement fest.|  
|[CComboBoxEx::SetWindowTheme](../Topic/CComboBoxEx::SetWindowTheme.md)|Legt den Stil des erweiterten Kombinationsfeldsteuerelements fest.|  
  
## Hinweise  
 Mit `CComboBoxEx` verwenden, um Kombinationsfeld\-Steuerelemente zu erstellen, müssen Sie nicht mehr eigenen Imagezeichnungscode implementieren.  Verwenden Sie stattdessen `CComboBoxEx`, für Bilder aus einer Bildliste zuzugreifen.  
  
## Bildlisten\-Unterstützung  
 In einem Standardkombinationsfeld ist der Besitzer des Kombinationsfelds zum Zeichnen eines Bilds verantwortlich, indem er das Kombinationsfeld als Ownerdrawnsteuerelement erstellt.  Wenn Sie `CComboBoxEx` verwenden, müssen Sie nicht, um die Zeichnungsformate **CBS\_OWNERDRAWFIXED** und **CBS\_HASSTRINGS** festzulegen, da sie impliziert werden.  Andernfalls müssen Sie Code schreiben, um Zeichenvorgänge auszuführen.  Ein `CComboBoxEx`\-Steuerelement unterstützt bis zu drei pro Element Bilder: ein für einen ausgewählten, eines für einen nicht ausgewählten Zustand und eine für ein Overlaybild.  
  
## Stile  
 `CComboBoxEx` unterstützt die Stile **CBS\_SIMPLE**, **CBS\_DROPDOWN**, **CBS\_DROPDOWNLIST** und **WS\_CHILD**.  Alle anderen übergebenen Formate, wenn Sie das Fenster erstellen, werden vom \- Steuerelement ignoriert.  Nachdem das Fenster erstellt wurde, können Sie andere Kombinationsfeldformate vom Aufrufen der `CComboBoxEx`\-Memberfunktion [SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md) bereitstellen.  Mit diesen Formaten können Sie:  
  
-   Festgelegte Suchen nach einer Zeichenfolge in der Liste, um die Groß\-\/Kleinschreibung beachtet wird.  
  
-   Erstellen Sie ein Kombinationsfeld\-Steuerelement verwendet, das den Schrägstrich \("\/"\), umgekehrter Schrägstrich \("\\ "\), und Punkt \(". "\) Zeichen als Worttrennzeichen.  Dadurch können Benutzer durch von Buchstabe für Buchstabe, mithilfe des Tastenkombination STRG\+\-PFEILS.  
  
-   Legen Sie das Kombinationsfeld\-Steuerelement entweder zur Anzeige oder ein Bild nicht anzuzeigen fest.  Wenn kein Bild angezeigt wird, kann das Kombinationsfeld den Texteinzug entfernen, der ein Bild enthält.  
  
-   Erstellen Sie ein schmales Kombinationsfeld\-Steuerelement, beispielsweise das Bearbeiten, sodass es überschreitet das Kombinationsfeld umfassendere ab, das es enthält.  
  
 Diese Formatflags werden weiter in [Verwenden CComboBoxEx](../../mfc/using-ccomboboxex.md) beschrieben.  
  
## Element\-Beibehaltungs\- und Rückruf\-Element\-Attribute  
 Elementinformationen, wie Indizes für Elemente und Bilder, Einzugswerte und Textzeichenfolgen, werden in der Win32\-Struktur [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) gespeichert, wie in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] beschrieben.  Die Struktur enthält außerdem Member, die den Rückrufflags entsprechen.  
  
 Eine ausführliche Erläuterung, konzeptionelle finden Sie unter [Verwenden CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## Anforderungen  
 **Header:** afxcmn.h  
  
## Siehe auch  
 [MFC\-Beispiel MFCIE](../../top/visual-cpp-samples.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)