---
title: Darstellung, ATL-Steuerelement-Assistent
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 4d3b0519951636fad4175dc35261ba35b3694ffa
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280406"
---
# <a name="appearance-atl-control-wizard"></a>Darstellung, ATL-Steuerelement-Assistent

Verwenden Sie diese Seite des Assistenten, um zusätzliche Benutzer-Element-Optionen für das Steuerelement zu identifizieren. Diese Seite ist verfügbar für Steuerelemente, die als **Standardsteuerelemente** unter **Steuerelementtyp** auf die [Optionen, ATL-Steuerelement-Assistent](../../atl/reference/options-atl-control-wizard.md) Seite.

## <a name="uielement-list"></a>UIElement-Liste

- **Anzeigestatus**

   Legt fest, die Darstellung des Steuerelements innerhalb des Containers.

   - **Nicht transparente**: Legt das bit im VIEWSTATUS_OPAQUE der [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) Enumeration und zeichnet das gesamte Steuerelement Rechteck an der [CComControlBase:: OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) Methode. Das Steuerelement wird vollständig deckend und keines der Container zeigt hinter der Steuerelementgrenzen.

      Mit dieser Einstellung können den Container schnell das Steuerelement zu zeichnen. Wenn diese Option nicht ausgewählt ist, kann das Steuerelement eine transparente Teile enthalten.

      Nur ein nicht transparentes Steuerelement kann es sich um eine Volltonfarbe für den Hintergrund haben.

   - **Volltonfarbe für den Hintergrund**: Legt das bit in der Enumeration VIEWSTATUS VIEWSTATUS_SOLIDBKGND fest. Der Hintergrund des Steuerelements wird als eine Volltonfarbe ohne Muster angezeigt.

      Diese Option steht nur, wenn die **nicht transparente** ebenfalls ausgewählt ist.

- **Fügen Sie basierend auf Steuerelement hinzu**

   Legt das Steuerelement auf einen Windows-Steuerelementtyp basieren, durch das Hinzufügen einer [CContainedWindow](ccontainedwindowt-class.md) Datenmember der Klasse, die Implementierung des Steuerelements. Es fügt auch einer meldungszuordnung und Meldungshandlerfunktionen um Windows-Meldungen für das Steuerelement zu verarbeiten. Wählen Sie aus der Liste den Typ des Windows-Steuerelements, die Sie erstellen, sofern vorhanden möchten.

   - **Button** (Schaltfläche)

   - **ListBox**

   - **SysAnimate32**

   - **SysListView32**

   - **ComboBox**

   - **RichEdit**

   - **SysDateTimePick32**

   - **SysMonthCal32**

   - **ComboBoxEx32**

   - **ScrollBar**

   - **SysHeader32**

   - **SysTabControl32**

   - **Bearbeiten**

   - **Static**

   - **SysIPAddress32**

   - **SysTreeView32**

- **Verschiedene status**

   Zusätzliche Aussehen und Verhalten-Optionen für das Steuerelement fest.

   - **Zur Laufzeit unsichtbar**: Legt das Steuerelement zur Laufzeit nicht sichtbar sein. Sie können Unsichtbare Steuerelemente verwenden, um Vorgänge im Hintergrund, wie z. B. das Auslösen von Ereignissen in festgelegten Intervallen auszuführen.

   - **Verhält sich wie Schaltfläche**: Setzt das bit im OLEMISC_ACTSLIKEBUTTON der [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Enumeration, um ein Steuerelement, das Verhalten zu aktivieren, wie eine Schaltfläche. Wenn der Container des Steuerelements Clientstandort als Standardschaltfläche gekennzeichnet wurde, ermöglicht die Auswahl dieser Option das Schaltflächen-Steuerelement selbst als Standardschaltfläche angezeigt, selbst mit einem breiteren Rahmen zu zeichnen. Finden Sie unter [CComControlBase:: GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) für Weitere Informationen.

   - **Verhält sich wie Bezeichnung**: Legt das OLEMISC_ACTSLIKELABEL bit in der OLEMISC-Enumeration zum Aktivieren eines Steuerelements für die systemeigene Bezeichnung des Containers zu ersetzen. Der Container bestimmt mit diesem Flag, wenn überhaupt.

- **Andere**

   Zusätzliches Verhalten-Optionen für das Steuerelement fest.

   - **Normalisiert DC**: Legt das Steuerelement einen normalisierten Gerätekontext zu erstellen, wenn sie aufgerufen wird, um sich selbst zu zeichnen. Diese Aktion standardisiert die Darstellung des Steuerelements, vereinfacht aber Zeichnung weniger effizient.

   - **Nur**: Gibt an, dass das Steuerelement nicht fensterlos sein kann. Wenn Sie diese Option nicht auswählen, das Steuerelement wird automatisch in Containern, die fensterlose Objekte unterstützen fensterlose, und es ist automatisch im Fenstermodus in Containern, die nicht über fensterlose Objekte unterstützen. Diese Option erzwingt, dass das Steuerelement im Fenstermodus, auch in Containern werden, die fensterlose Objekte zu unterstützen.

   - **Einfügbare**: Wählen Sie diese Option, damit das Steuerelement angezeigt werden die **Objekt einfügen** Dialogfeld Anwendungen wie Word und Excel. Das Steuerelement kann dann von jeder Anwendung eingefügt werden, die eingebettete Objekte über dieses Dialogfeld unterstützt.

## <a name="see-also"></a>Siehe auch

[ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT-Beispiel: Eine übergeordnete Klasse für ein Standard-Windows-Steuerelement](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
