---
title: Darstellung, ATL-Steuerelement-Assistent
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: e07dc017241848f1a670c17b12c2254de6d1b8e1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492191"
---
# <a name="appearance-atl-control-wizard"></a>Darstellung, ATL-Steuerelement-Assistent

Verwenden Sie diese Seite des Assistenten, um zusätzliche Benutzer Element Optionen für das Steuerelement zu identifizieren. Diese Seite ist für Steuerelemente verfügbar, die auf der Seite [Optionen, ATL-Steuer](../../atl/reference/options-atl-control-wizard.md) Element-Assistent als **Standard Steuerelemente** unter Steuerungstyp identifiziert werden.

## <a name="uielement-list"></a>Liste der Benutzeroberflächenelemente

- **Status anzeigen**

   Legt die Darstellung des Steuer Elements im Container fest.

   - Nicht transparent: Legt das VIEWSTATUS_OPAQUE-Bit in der [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) -Enumeration fest und zeichnet das gesamte Steuerelement Rechteck, das an die [CComControlBase:: OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) -Methode übergeben wird. Das-Steuerelement wird vollständig nicht transparent angezeigt, und der Container wird hinter den Steuerelement Grenzen nicht angezeigt.

      Mit dieser Einstellung kann der Container das Steuerelement schneller zeichnen. Wenn diese Option nicht ausgewählt ist, kann das Steuerelement transparente Teile enthalten.

      Nur ein undurchsichtiges Steuerelement kann über einen voll soliden Hintergrund verfügen.

   - Voll **solider Hintergrund**: Legt das VIEWSTATUS_SOLIDBKGND-Bit in der VIEWSTATUS-Enumeration fest. Der Hintergrund des Steuer Elements wird als voll Tonfarbe ohne Muster angezeigt.

      Diese Option ist nur verfügbar, wenn die Option nicht transparent ausgewählt ist.

- **Steuerelement hinzufügen basierend auf**

   Legt fest, dass das Steuerelement auf einem Windows-Steuer Elementtyp basiert, indem der Klasse, die das Steuerelement implementiert, ein [CContainedWindow](ccontainedwindowt-class.md) -Datenmember hinzugefügt Außerdem werden eine nachrichtenmap und nachrichtenhandlerfunktionen zum Verarbeiten von Windows-Meldungen für das Steuerelement hinzugefügt. Wählen Sie in der Liste den Typ des Windows-Steuer Elements aus, den Sie erstellen möchten (sofern vorhanden).

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

- **Misc-Status**

   Legt zusätzliche Optionen für Darstellung und Verhalten für das-Steuerelement fest.

   - **Unsichtbar zur Laufzeit**: Legt fest, dass das Steuerelement zur Laufzeit unsichtbar ist. Sie können nicht sichtbare Steuerelemente verwenden, um Vorgänge im Hintergrund auszuführen, z. b. das Auslösen von Ereignissen in zeitgesteuerten Intervallen.

   - **Verhält sich wie Schaltfläche**: Legt das OLEMISC_ACTSLIKEBUTTON-Bit in der [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) -Enumeration fest, damit ein Steuerelement wie eine Schaltfläche ausgeführt werden kann. Wenn der Container die Client Site des Steuer Elements als Standard Schaltfläche markiert hat, ermöglicht die Auswahl dieser Option dem Schaltflächen-Steuerelement, sich selbst als Standard Schaltfläche anzuzeigen, indem es sich mit einem dickeren Rahmen zeichnet. Weitere Informationen finden Sie unter [CComControlBase:: GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) .

   - **Verhält sich wie die Bezeichnung**: Legt das OLEMISC_ACTSLIKELABEL-Bit in der OLEMISC-Enumeration fest, damit ein Steuerelement die systemeigene Bezeichnung des Containers ersetzen kann. Der Container bestimmt, was mit diesem Flag geschehen soll, sofern nichts.

- **Andere**

   Legt zusätzliche Verhaltens Optionen für das-Steuerelement fest.

   - **Normalisierter DC**: Legt fest, dass das Steuerelement einen normalisierten Gerätekontext erstellt, wenn es aufgerufen wird, um sich selbst zu zeichnen. Durch diese Aktion wird die Darstellung des Steuer Elements standardisiert, aber das Zeichnen ist weniger effizient.

   - **Nur Fenster**: Gibt an, dass das Steuerelement nicht fensterlose sein darf. Wenn Sie diese Option nicht auswählen, wird das Steuerelement in Containern, die fensterlose Objekte unterstützen, automatisch fensterloser angezeigt, und es wird automatisch in Containern angezeigt, die keine fensterlosen Objekte unterstützen. Wenn Sie diese Option auswählen, wird auch in Containern, die fensterlose Objekte unterstützen, das Fenster des Steuer Elements angezeigt.

   - **Insertable**: Wählen Sie diese Option aus, damit das Steuerelement im Dialogfeld **Objekt einfügen** von Anwendungen wie Word und Excel angezeigt wird. Das Steuerelement kann dann von jeder Anwendung eingefügt werden, die eingebettete Objekte in diesem Dialogfeld unterstützt.

## <a name="see-also"></a>Siehe auch

[ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT-Beispiel: SuperClasses a Standard Windows-Steuerelement](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
