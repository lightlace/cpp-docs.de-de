---
title: "Darstellung, ATL-Steuerelement-Assistent"
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
  - "vc.codewiz.class.atl.control.misc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Steuerelement-Assistent, Darstellung"
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Darstellung, ATL-Steuerelement-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügen Sie die Zusammenfassung der Suchergebnisse hier ein.  
  
 Sie verwenden diese Seite des Assistenten, um zusätzliche Benutzerelementoptionen für das Steuerelement festzulegen.  Diese Seite ist für Steuerelemente verfügbar, die auf der Seite [Optionen, ATL\-Steuerelement\-Assistent](../../atl/reference/options-atl-control-wizard.md) unter **Steuerelementtyp** als **Standardsteuerelement** konfiguriert wurden.  
  
## UIElement-Liste  
 **Ansichtsstatus**  
 Legt das Erscheinungsbild des Steuerelements innerhalb des Containers fest.  
  
-   **Opaque**: Legt das `VIEWSTATUS_OPAQUE`\-Bit in der [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)\-Enumeration fest und zeichnet das gesamte, an die [CComControlBase::OnDraw](../Topic/CComControlBase::OnDraw.md)\-Methode übergebene Steuerelement\-Rechteck.  Das Steuerelement wird völlig deckend dargestellt, und es sind keine Container hinter den Begrenzungen des Steuerelements zu sehen.  
  
     Diese Einstellung ermöglicht es dem Container, das Steuerelement schneller zu zeichnen.  Wenn die Option nicht aktiviert ist, kann das Steuerelement teilweise transparent sein.  
  
     Nur ein nicht transparentes Steuerelement kann einen Hintergrund in einer Volltonfarbe haben.  
  
-   Legt das `VIEWSTATUS_SOLIDBKGND`\-Bit in der `VIEWSTATUS`\-Enumeration fest.  Der Hintergrund des Steuerelements wird in einer Volltonfarbe ohne Muster dargestellt.  
  
     Diese Option ist nur verfügbar, wenn auch die Option **Opaque** ausgewählt ist.  
  
 **Steuerelement hinzufügen, das auf Folgendem basiert**  
 Legt fest, dass das Steuerelement auf einem Windows\-Steuerelementtyp basiert. Dazu wird der Klasse, durch die das Steuerelement implementiert wird, ein [CContainedWindow](../Topic/CContainedWindow.md)\-Datenmember hinzugefügt.  Darüber hinaus werden eine Meldungszuordnung sowie Meldungshandlerfunktionen hinzugefügt, um Windows\-Meldungen für das Steuerelement zu verarbeiten.  Wählen Sie ggf. den Typ des zu erstellenden Windows\-Steuerelements aus der Liste aus.  
  
-   `Button`  
  
-   `ListBox`  
  
-   `SysAnimate32`  
  
-   `SysListView32`  
  
-   `ComboBox`  
  
-   `RichEdit`  
  
-   `SysDateTimePick32`  
  
-   `SysMonthCal32`  
  
-   `ComboBoxEx32`  
  
-   `ScrollBar`  
  
-   `SysHeader32`  
  
-   `SysTabControl32`  
  
-   `Edit`  
  
-   `Static`  
  
-   `SysIPAddress32`  
  
-   `SysTreeView32`  
  
 **Allgemeiner Status**  
 Legt zusätzliche Optionen für die Darstellung und das Verhalten des Steuerelements fest.  
  
-   **Unsichtbar während Laufzeit**: Legt fest, dass das Steuerelement zur Laufzeit unsichtbar ist.  Sie können unsichtbare Steuerelemente verwenden, um Operationen im Hintergrund auszuführen, z. B. das Auslösen von Ereignissen in festgelegten Zeitabständen.  
  
-   **Verhält sich wie eine Schaltfläche**: Legt das `OLEMISC_ACTSLIKEBUTTON`\-Bit in der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)\-Enumeration fest und ermöglicht es dem Steuerelement, das Verhalten einer Schaltfläche anzunehmen.  Wenn im Container die Clientposition des Steuerelements als Standardschaltfläche gekennzeichnet ist, wird das Schaltflächen\-Steuerelement mit dieser Option als Standardschaltfläche angezeigt, indem es mit einem breiteren Rahmen gezeichnet wird.  Weitere Informationen finden Sie unter [CComControlBase::GetAmbientDisplayAsDefault](../Topic/CComControlBase::GetAmbientDisplayAsDefault.md).  
  
-   **Verhält sich wie eine Bezeichnung**: Legt das `OLEMISC_ACTSLIKELABEL`\-Bit in der `OLEMISC`\-Enumeration fest und ermöglicht es dem Steuerelement, die systemeigene Bezeichnung des Containers zu ersetzen.  Der Container bestimmt, wie dieses Flag behandelt werden soll.  
  
 **Andere**  
 Legt weitere Verhaltensoptionen für das Steuerelement fest.  
  
-   **Normalisiertes DC**: Legt fest, dass das Steuerelement einen normalen Gerätekontext erstellt, wenn es gezeichnet wird.  Dadurch wird die Darstellung des Steuerelements zwar standardisiert, das Zeichnen des Steuerelements ist jedoch weniger effizient.  
  
-   **Nur als Fenster**: Legt fest, dass das Steuerelement nicht fensterlos sein kann.  Wenn diese Option deaktiviert ist, wird das Steuerelement in Containern, die fensterlose Objekte unterstützen, automatisch ohne Fenster und in Containern, die keine fensterlosen Objekte unterstützen, automatisch mit Fenster dargestellt.  Wenn diese Option aktiviert ist, wird das Steuerelement auch in Containern, die fensterlose Objekte unterstützen, immer mit Fenster dargestellt.  
  
-   **Einfügbar**: Wählen Sie diese Option, damit das Steuerelement in Anwendungen wie Word oder Excel im Dialogfeld **Objekt einfügen** angezeigt wird.  Das Steuerelement kann in jeder Anwendung, die eingebettete Objekte unterstützt, mithilfe dieses Dialogfelds eingefügt werden.  
  
## Siehe auch  
 [ATL\-Steuerelement\-Assistent](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT Sample: Superclasses a Standard Windows Control](assetId:///30e46bdc-ed92-417c-b6b8-359017265a7b)