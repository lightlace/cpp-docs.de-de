---
title: "CCmdUI Class"
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
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schaltflächen [C++], Aktualisieren bei Kontextänderungen"
  - "CCmdUI class"
  - "command user interface"
  - "Befehle [C++], updating UI"
  - "menus [C++], Aktualisieren bei Kontextänderungen"
  - "Zustände, updating user interface object"
  - "Symbolleisten [C++], Aktualisieren"
  - "updating user interfaces for commands"
  - "Benutzeroberflächen, Aktualisieren"
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ist nur innerhalb eines `ON_UPDATE_COMMAND_UI`\-Handlers in `CCmdTarget` von abgeleitete Klasse verwendet.  
  
## Syntax  
  
```  
class CCmdUI  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCmdUI::ContinueRouting](../Topic/CCmdUI::ContinueRouting.md)|Weist den BefehlRouting Mechanismus mit, um das Weiterleiten der aktuellen Meldung in der Kette von Handlern fortzusetzen.|  
|[CCmdUI::Enable](../Topic/CCmdUI::Enable.md)|Aktiviert oder deaktiviert das Benutzeroberflächen\-Element für diesen Befehl.|  
|[CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)|Legt den Aktivierungszustand des Benutzeroberflächeelements für diesen Befehl fest.|  
|[CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)|Wie die `SetCheck`\-Memberfunktion jedoch wendet an Radiogruppen.|  
|[CCmdUI::SetText](../Topic/CCmdUI::SetText.md)|Legt den Text für das Benutzeroberflächen\-Element für diesen Befehl fest.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCmdUI::m\_nID](../Topic/CCmdUI::m_nID.md)|Die ID des Benutzeroberflächeobjekts.|  
|[CCmdUI::m\_nIndex](../Topic/CCmdUI::m_nIndex.md)|Der Index des Benutzeroberflächeobjekts.|  
|[CCmdUI::m\_pMenu](../Topic/CCmdUI::m_pMenu.md)|Punkte im Menü, das von `CCmdUI` dargestellt wird, ein Objekt.|  
|[CCmdUI::m\_pOther](../Topic/CCmdUI::m_pOther.md)|Zeigt auf den Fensterobjekt, das die Benachrichtigung gesendet.|  
|[CCmdUI::m\_pSubMenu](../Topic/CCmdUI::m_pSubMenu.md)|Zeigt auf das enthaltene Untermenü, das von `CCmdUI` dargestellt wird, ein Objekt.|  
  
## Hinweise  
 `CCmdUI` hat keine Basisklasse.  
  
 Wenn ein Benutzer der Bedarfe der Anwender unten ein Menü, jedes Menüelement muss wissen, ob es angezeigt werden soll, wenn aktiviert oder deaktiviert.  Das Ziel eines Menübefehls stellt diese Informationen aus dem Implementieren eines Handlers `ON_UPDATE_COMMAND_UI` bereit.  Für jedes der Befehlsbenutzeroberflächeobjekte in der Anwendung, verwenden Sie das Eigenschaftenfenster, um einen Eintrag in der Meldungszuordnung und einen Funktionsprototyp für jeden Handler zu erstellen.  
  
 Wenn das Menü heruntergezogen wird, zeigt die Frameworksuchen für und die Aufrufe `CCmdUI`\-Memberfunktionen jedes `ON_UPDATE_COMMAND_UI`\-Handlers, der Aufrufe jedes Handlers wie **Enable** und **Check** und Framework dann entsprechend jedes Menüelement an.  
  
 Ein Menüelement kann durch eine Steuerleistenschaltfläche oder anderes Befehlsbenutzeroberflächeobjekt ersetzt werden, ohne den Code innerhalb des Handlers `ON_UPDATE_COMMAND_UI` zu ändern.  
  
 In der folgenden Tabelle werden die Effekte zusammengefasst, die die `CCmdUI`\-Memberfunktionen auf verschiedene Befehlsbenutzeroberflächeelemente haben.  
  
|Benutzeroberflächenelement|Aktivieren|SetCheck|SetRadio|SetText|  
|--------------------------------|----------------|--------------|--------------|-------------|  
|Menüelement|Aktiviert oder deaktiviert|Überprüfungen \(×\) oder deaktiviert|Überprüfungen mithilfe von Punktdirektiven \(•\)|Legt Elementtext fest|  
|Schaltfläche für Symbolleiste|Aktiviert oder deaktiviert|Wählt aus, wählt ab, oder unbestimmt|Identisch mit `SetCheck`|\(Nicht zutreffend\)|  
|Statusleistenbereich|Macht Text sichtbar oder nicht sichtbar|Legt Knall\-heraus oder normalen Rahmen fest|Identisch mit `SetCheck`|Legt Bereichstext fest|  
|Normale Schaltfläche in `CDialogBar`|Aktiviert oder deaktiviert|Überprüfungen oder Kontrollkästchen deaktiviert|Identisch mit `SetCheck`|Sätze Schaltfläche Text|  
|Normales Steuerelement in `CDialogBar`|Aktiviert oder deaktiviert|\(Nicht zutreffend\)|\(Nicht zutreffend\)|Legt Fenstertext fest|  
  
 Weitere bei der Verwendung von dieser Klasse, finden Sie unter [Wie Benutzeroberflächenobjekte aktualisiert](../../mfc/how-to-update-user-interface-objects.md).  
  
## Vererbungshierarchie  
 `CCmdUI`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel\-MDI](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)