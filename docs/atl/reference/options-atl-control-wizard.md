---
title: Optionen, ATL-Steuerelement-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.options
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
ms.openlocfilehash: 932661227daa216934c061a8b6807b05ca8270ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443757"
---
# <a name="options-atl-control-wizard"></a>Optionen, ATL-Steuerelement-Assistent

Fügen Sie hier "Suchergebnisse" Zusammenfassung.

Mithilfe dieser Seite des Assistenten können Sie um den Typ des Steuerelements zu definieren, die Sie erstellen, und die Ebene der Unterstützung von Schnittstellen enthält.

## <a name="uielement-list"></a>UIElement-Liste

### <a name="control-type"></a>Steuerelementtyp

Die Art des Steuerelements, das Sie erstellen möchten.

- **Standardsteuerelement**: ein ActiveX-Steuerelement.

- **Zusammengesetztes Steuerelement**: ein ActiveX-Steuerelement, das (ähnlich wie ein Dialogfeld, das) enthalten, kann andere ActiveX-Steuerelemente oder Windows-Steuerelemente. Ein zusammengesetztes Steuerelement umfasst Folgendes:

   - Eine Vorlage für das Dialogfeld, das das zusammengesetzte Steuerelement implementiert werden soll.

   - Eine benutzerdefinierte Ressource, Registrierung, die automatisch registriert, das zusammengesetzte Steuerelement aufgerufen.

   - Eine C++-Klasse, die das zusammengesetzte Steuerelement implementiert.

   - Eine COM-Schnittstelle, die vom zusammengesetzten Steuerelement verfügbar gemacht.

   - Ein HTML-Testseite, die das zusammengesetzte Steuerelement enthält.

   Dieses Steuerelement legt standardmäßig [CComControlBase](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) auf "true", um anzugeben, dass dies ein Steuerelement mit Fenster ist. Eine Zuordnung für die Senke implementiert. Weitere Informationen finden Sie unter [-Unterstützung für DHTML-Steuerelement](../../atl/atl-support-for-dhtml-controls.md).

- **DHTML-Steuerelements**: Gibt an, ein ATL-DHTML-Steuerelement der Benutzeroberfläche mithilfe von HTML. DHTML-UI-Klasse enthält eine COM-Zuordnung. Dieses Steuerelement legt standardmäßig [CComControlBase](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) auf "true", um anzugeben, dass dies ein Steuerelement mit Fenster ist.

   Weitere Informationen finden Sie unter [Identifizieren von Elementen des DHTML-Steuerelementprojekts](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).

### <a name="minimal-control"></a>Nur minimale Kontrolle

Unterstützt nur die Schnittstellen, die meisten Container absolut erforderlich sind. Sie können festlegen, **nur minimale Kontrolle** für alle der Steuerelementtypen: Sie können ein minimal standard-Steuerelement, einem minimalen zusammengesetzten Steuerelement oder ein minimal DHTML-Steuerelement erstellen.

### <a name="aggregation"></a>Aggregation

Fügt die Unterstützung für das Steuerelement, das Sie erstellen. Weitere Informationen finden Sie unter [Aggregation](../../atl/aggregation.md).

- **Ja**: Erstellen eines Steuerelements, die aggregiert werden können.

- **Keine**: Erstellen Sie ein Steuerelement, das nicht aggregiert werden kann.

- **Nur**: Erstellen Sie ein Steuerelement, das durch die Aggregation nur instanziiert werden kann.

### <a name="threading-model"></a>Threadmodell

Gibt an, dass das Threadingmodell vom Steuerelement verwendet.

- **Einzelne**: das Steuerelement wird nur im primären COM-Thread ausgeführt.

- **Apartment**: das Steuerelement kann in jedem Singlethread-Apartment erstellt werden. Der Standardwert.

### <a name="interface"></a>Interface

Der Typ der Schnittstelle, die dieses Steuerelement in den Container verfügbar macht.

- **Duale**: erstellt eine Schnittstelle, die Eigenschaften und Methoden über verfügbar macht `IDispatch` und direkt über von der VTBL.

- **Benutzerdefinierte**: erstellt eine Schnittstelle, die Methoden, die direkt durch eine VTBL verfügbar macht.

   Bei Auswahl von **benutzerdefinierte**, können Sie angeben, dass das Steuerelement **Automatisierungskompatibel**. Bei Auswahl von **Automatisierungskompatibel**, fügt der Assistent die [Oleautomation](../../windows/oleautomation.md) -Attribut auf die Schnittstelle in der IDL-Datei, und die Schnittstelle durch den universellen Marshaller in oleaut32.dll gemarshallt werden kann. Finden Sie unter [Marshaling Details](/windows/desktop/com/marshaling-details) im Windows SDK für Weitere Informationen.

   Darüber hinaus bei Auswahl von **Automatisierungskompatibel**, und klicken Sie dann alle Parameter für alle Methoden des Steuerelements Variant-Wert sein müssen kompatibel.

### <a name="support"></a>Unterstützung

Legt zusätzliche sonstige Unterstützung für das Steuerelement fest.

- **Verbindungspunkte**: können Sie dazu die Klasse des Objekts abgeleitet Verbindungspunkte für Ihr Objekt [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) und ermöglicht es, eine Schnittstelle verfügbar zu machen.

- **Lizenzierte**: Fügt Unterstützung für das Steuerelement für [Lizenzierung](/windows/desktop/com/licensing). Lizenzierte Steuerelemente können nur gehostet werden, wenn der Client-Computer die richtige Lizenz verfügt.

## <a name="see-also"></a>Siehe auch

[ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)

