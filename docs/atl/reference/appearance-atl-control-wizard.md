---
title: Darstellung, ATL-Steuerelement-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1d27b46f529d8423bdaf733928a9f3e46b3f185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="appearance-atl-control-wizard"></a>Darstellung, ATL-Steuerelement-Assistent
"Suchergebnisse" Zusammenfassung hier einfügen.  
  
 Verwenden Sie diese Seite des Assistenten, um zusätzliche Befehlszeilenoptionen für Element für das Steuerelement zu identifizieren. Diese Seite steht für Steuerelemente, die als gekennzeichnete **Standardsteuerelemente** unter **Steuerelementtyp** auf die [Optionen, ATL-Steuerelement-Assistent](../../atl/reference/options-atl-control-wizard.md) Seite.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Anzeigestatus**  
 Legt das Erscheinungsbild des Steuerelements innerhalb des Containers fest.  
  
-   **Deckend**: Legt die `VIEWSTATUS_OPAQUE` bit in der [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) -Enumeration und zeichnet das gesamte Steuerelement Rechteck an die [CComControlBase:: OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) Methode. Das Steuerelement wird vollständig deckend und keines der Container hinter der Steuerelementgrenzen veranschaulicht.  
  
     Mit dieser Einstellung wird den Container des Steuerelements schneller zu zeichnen. Wenn diese Option nicht ausgewählt ist, kann das Steuerelement transparent Teile enthalten.  
  
     Nur ein nicht transparentes Steuerelement kann einen Volltonfarbe für den Hintergrund haben.  
  
-   Legt die `VIEWSTATUS_SOLIDBKGND` bit in der `VIEWSTATUS` Enumeration. Der Hintergrund des Steuerelements wird als eine Volltonfarbe mit keinem Muster angezeigt.  
  
     Diese Option steht nur, wenn die **nicht transparenten** ebenfalls ausgewählt ist.  
  
 **Fügen Sie auf der Grundlage Steuerelement hinzu**  
 Legt das Steuerelement auf ein Windows-Steuerelementtyp basieren, durch Hinzufügen einer [CContainedWindow](ccontainedwindowt-class.md) Datenmember der Klasse, die das Steuerelement implementieren. Darüber hinaus wird eine meldungszuordnung und Meldungshandlerfunktionen behandelt Windows-Meldungen für das Steuerelement hinzugefügt. Wählen Sie aus der Liste den Typ des Windows-Steuerelements, die Sie erstellen, falls vorhanden möchten.  

  
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
  
 **Verschiedenes-status**  
 Legt zusätzliche Optionen für Aussehen und Verhalten für das Steuerelement fest.  
  
-   **Zur Laufzeit unsichtbar**: Legt das Steuerelement zur Laufzeit nicht sichtbar sein. Unsichtbare Steuerelemente können Vorgänge im Hintergrund, z. B. das Auslösen von Ereignissen in festgelegten Intervallen ausgeführt werden.  
  
-   **Verhält sich wie die Schaltfläche**: Legt die `OLEMISC_ACTSLIKEBUTTON` bit in der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Enumeration, um ein Steuerelement, das Verhalten zu aktivieren, wie z. B. eine Schaltfläche. Wenn der Container des Steuerelements Clientstandort als Standardschaltfläche markiert, ermöglicht das Auswählen dieser Option das Schaltflächen-Steuerelement selbst als Standardschaltfläche anzeigen, indem Sie zeichnen sich selbst mit einem breiteren Rahmen aus. Finden Sie unter [CComControlBase:: GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) für Weitere Informationen.  
  
-   **Verhält sich wie Bezeichnung**: Legt die `OLEMISC_ACTSLIKELABEL` bit in der `OLEMISC` Enumeration zum Aktivieren eines Steuerelements für die systemeigene Bezeichnung des Containers zu ersetzen. Der Container bestimmt, wie mit diesem Flag geschehen soll, wenn nichts.  
  
 **Andere**  
 Legt zusätzliche Optionen für das Steuerelement fest.  
  
-   **Normalisiert DC**: Legt das Steuerelement um einen normalisierten Gerätekontext zu erstellen, wenn sie aufgerufen wird, um sich selbst zu zeichnen. Diese Aktion standardisiert die Darstellung des Steuerelements, vereinfacht aber Zeichnung weniger effizient.  
  
-   **Fenster nur**: Gibt an, dass das Steuerelement fensterlose sein kann. Wenn Sie diese Option nicht auswählen, das Steuerelement wird automatisch in Containern, die fensterlose Objekte unterstützen fensterlose, und es wird automatisch im Fenstermodus in Containern, die keine fensterlosen Objekte unterstützen. Nach Auswahl dieser Option erzwingt, dass das Steuerelement im Fenstermodus selbst im Container sein, die fensterlose Objekte unterstützen.  
  
-   **Einfügbar**: Wählen Sie diese Option aus, damit das Steuerelement angezeigt werden die **Objekt einfügen** Dialogfeld von Anwendungen wie Word und Excel. Das Steuerelement kann dann von einer Anwendung eingefügt werden, die eingebettete Objekte über dieses Dialogfeld unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT-Beispiel: Erstellt eine übergeordnete Klasse für ein Windows-Standardsteuerelement](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)

