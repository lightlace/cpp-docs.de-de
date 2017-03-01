---
title: Darstellung, ATL-Steuerelement-Assistenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: dde27a7b62f3ee3b5fe8fcacd8141e9f89ed3c98
ms.lasthandoff: 02/24/2017

---
# <a name="appearance-atl-control-wizard"></a>Darstellung, ATL-Steuerelement-Assistent
"Suchergebnisse" Zusammenfassung hier einfügen.  
  
 Verwenden Sie diese Seite des Assistenten, um zusätzliche Benutzer-Element-Optionen für das Steuerelement zu identifizieren. Diese Seite ist verfügbar für Steuerelemente, die als **Standardsteuerelemente** unter **Steuerelementtyp** auf der [Optionen, ATL-Steuerelement-Assistent](../../atl/reference/options-atl-control-wizard.md) Seite.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Anzeigen des status**  
 Legt das Erscheinungsbild des Steuerelements innerhalb des Containers fest.  
  
-   **Nicht transparente**: Legt die `VIEWSTATUS_OPAQUE` bit in der [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) -Enumeration und zeichnet das gesamte Steuerelement Rechteck an der [CComControlBase:: OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) Methode. Das Steuerelement wird transparent, und keines der Container zeigt hinter der Steuerelementgrenzen.  
  
     Mit dieser Einstellung wird den Container des Steuerelements schneller zu zeichnen. Wenn diese Option nicht ausgewählt ist, kann das Steuerelement teilweise transparent sein.  
  
     Nur ein nicht transparentes Steuerelement kann einen Volltonfarbe für den Hintergrund haben.  
  
-   Legt die `VIEWSTATUS_SOLIDBKGND` bit in der `VIEWSTATUS` Enumeration. Der Hintergrund des Steuerelements wird als eine Volltonfarbe ohne Muster angezeigt.  
  
     Diese Option steht nur dann, wenn die **nicht transparenten** ebenfalls ausgewählt ist.  
  
 **Hinzufügen des Steuerelements basierend auf**  
 Legt das Steuerelement, das auf einem Windows-Steuerelementtyp basiert eine [CContainedWindow](ccontainedwindowt-class.md) -Datenmember der Klasse des Steuerelements. Außerdem wird eine Nachricht Karte und Meldungshandlerfunktionen, Windows-Meldungen für das Steuerelement behandeln hinzugefügt. Wählen Sie aus der Liste der Windows-Steuerelement, das Sie erstellen falls vorhanden, möchten.  

  
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
  
 **Allgemeiner status**  
 Zusätzliche Aussehen und Verhalten-Optionen für das Steuerelement fest.  
  
-   **Zur Laufzeit unsichtbar**: Legt das Steuerelement zur Laufzeit unsichtbar ist. Unsichtbare Steuerelemente können Vorgänge im Hintergrund, z. B. das Auslösen von Ereignissen in festgelegten Intervallen ausgeführt werden.  
  
-   **Verhält sich wie die Schaltfläche**: Legt die `OLEMISC_ACTSLIKEBUTTON` bit in der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) -Enumeration, die ein Steuerelement, das Verhalten wie eine Schaltfläche. Wenn der Container des Steuerelements Clientstandort als Standardschaltfläche markiert, ermöglicht das Auswählen dieser Option das Schaltflächen-Steuerelement selbst als Standardschaltfläche zeichnen sich selbst mit einem breiteren Rahmen angezeigt. Finden Sie unter [CComControlBase:: GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) Weitere Informationen.  
  
-   **Verhält sich wie die Bezeichnung**: Legt die `OLEMISC_ACTSLIKELABEL` bit in der `OLEMISC` -Enumeration, die ein Steuerelement, das systemeigene Bezeichnung des Containers zu ersetzen. Der Container bestimmt, wie Sie mit diesem Flag nichts.  
  
 **Andere**  
 Zusätzliche Optionen für das Steuerelement fest.  
  
-   **Normalisiertes DC**: Legt das Steuerelement einen normalisierten Gerätekontext erstellt, wenn sie aufgerufen wird, um sich selbst zu zeichnen. Diese Aktion standardisiert die Darstellung des Steuerelements, aber es macht Zeichnung weniger effizient.  
  
-   **Nur**: Gibt an, dass das Steuerelement nicht fensterlos sein kann. Wenn Sie diese Option nicht auswählen, das Steuerelement wird automatisch in Containern, die fensterlose Objekte unterstützen fensterlose und automatisch im Fenstermodus in Containern, die keine fensterlosen Objekte unterstützen kann. Wenn Sie diese Option auswählen, wird das Steuerelement, im Fenstermodus, auch in Containern, die fensterlose Objekte unterstützen.  
  
-   **Einfügbar**: Wählen Sie diese Option, um das Steuerelement im angezeigt werden die **Objekt einfügen** Dialogfeld Clientanwendungen wie Word und Excel. Das Steuerelement kann dann von jeder Anwendung eingefügt werden, die eingebettete Objekte über dieses Dialogfeld unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT-Beispiel: Erstellt eine übergeordnete Klasse für ein Windows-Standardsteuerelement](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)


