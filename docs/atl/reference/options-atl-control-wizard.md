---
title: Optionen, ATL-Steuerelement-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.options
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
ms.openlocfilehash: 25db3995687011de5e9cc0a98506cd26f2f1af0b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495443"
---
# <a name="options-atl-control-wizard"></a>Optionen, ATL-Steuerelement-Assistent

Verwenden Sie diese Seite des Assistenten, um den Typ des Steuer Elements zu definieren, das Sie erstellen, und die Ebene der Schnittstellen Unterstützung, die es enthält.

## <a name="uielement-list"></a>Liste der Benutzeroberflächenelemente

### <a name="control-type"></a>Steuerelementtyp

Die Art des Steuer Elements, das Sie erstellen möchten.

- **Standard Steuer**Element: Ein ActiveX-Steuerelement.

- **Composite-Steuer**Element: Ein ActiveX-Steuerelement, das (ähnlich einem Dialogfeld) andere ActiveX-Steuerelemente oder Windows-Steuerelemente enthalten kann. Ein zusammengesetztes Steuerelement schließt Folgendes ein:

  - Eine Vorlage für das Dialogfeld, das das zusammengesetzte Steuerelement implementiert.

  - Eine benutzerdefinierte Ressource, die Registrierung, die das zusammengesetzte Steuerelement automatisch registriert, wenn es aufgerufen wird.

  - Eine C++ Klasse, die das zusammengesetzte Steuerelement implementiert.

  - Eine vom zusammengesetzten Steuerelement verfügbar gemachte COM-Schnittstelle.

  - Eine HTML-Testseite, die das zusammengesetzte Steuerelement enthält.

    Standardmäßig legt dieses Steuerelement " [CComControlBase:: m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) " auf "true" fest, um anzugeben, dass es sich hierbei um ein Fenster Steuerelement handelt. Es implementiert eine Sink map. Weitere Informationen finden Sie [unter Unterstützung für DHTML-Steuer](../../atl/atl-support-for-dhtml-controls.md)Elemente.

- **DHTML-Steuer**Element: Ein ATL-DHTML-Steuerelement gibt die Benutzeroberfläche mithilfe von HTML an. Die DHTML-UI-Klasse enthält eine COM-Zuordnung. Standardmäßig legt dieses Steuerelement " [CComControlBase:: m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) " auf "true" fest, um anzugeben, dass es sich hierbei um ein Fenster Steuerelement handelt.

   Weitere Informationen finden Sie unter [Identifizieren der Elemente des DHTML-Steuerelement Projekts](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).

### <a name="minimal-control"></a>Minimale Kontrolle

Unterstützt nur die Schnittstellen, die von den meisten Containern absolut benötigt werden. Sie können für alle Steuerelement Typen eine **minimale Kontrolle** festlegen: Sie können ein minimal-Standard Steuerelement, ein minimal zusammengesetztes Steuerelement oder ein minimales DHTML-Steuerelement erstellen.

### <a name="aggregation"></a>Aggregation

Fügt Aggregations Unterstützung für das Steuerelement hinzu, das Sie erstellen. Weitere Informationen finden Sie unter [Aggregation](../../atl/aggregation.md).

- **Ja**: Erstellen Sie ein Steuerelement, das aggregiert werden kann.

- **Nein**: Erstellen Sie ein Steuerelement, das nicht aggregiert werden kann.

- **Nur**: Erstellen Sie ein Steuerelement, das nur durch Aggregation instanziiert werden kann.

### <a name="threading-model"></a>Threadmodell

Gibt das Threading Modell an, das vom-Steuerelement verwendet wird.

- **Single**: Das-Steuerelement wird nur im primären com-Thread ausgeführt.

- **Apartment**: Das-Steuerelement kann in jedem einzelnen Thread-Apartment erstellt werden. Der Standardwert.

### <a name="interface"></a>Interface

Der Typ der Schnittstelle, die dieses Steuerelement für den Container verfügbar macht.

- **Dual**: Erstellt eine Schnittstelle, die Eigenschaften und Methoden `IDispatch` durch und direkt über das VTBL verfügbar macht.

- **Benutzerdefiniert**: Erstellt eine Schnittstelle, die Methoden direkt über ein VTBL verfügbar macht.

   Wenn Sie **Benutzer**definiert auswählen, können Sie angeben, dass das Steuerelement **Automatisierungs kompatibel**ist. Wenn Sie **Automation-kompatibel**auswählen, fügt der Assistent der-Schnittstelle in der IDL das [oleautomation](../../windows/oleautomation.md) -Attribut hinzu, und die-Schnittstelle kann vom Universal Mars Haller in Oleaut32. dll gemarshallt werden. Weitere Informationen finden Sie unter Mars Hallen von [Details](/windows/win32/com/marshaling-details) in der Windows SDK.

   Wenn Sie außerdem **Automatisierungs kompatibel**auswählen, müssen alle Parameter für alle Methoden im Steuerelement Variant-kompatibel sein.

### <a name="support"></a>Unterstützung

Legt weitere verschiedene Unterstützung für das-Steuerelement fest.

- **Verbindungspunkte**: Aktiviert Verbindungspunkte für Ihr Objekt, indem die Klasse des Objekts von [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) abgeleitet und eine Quell Schnittstelle verfügbar gemacht wird.

- **Lizenziert**: Fügt dem-Steuerelement Unterstützung für die [Lizenzierung](/windows/win32/com/licensing)hinzu. Lizenzierte Steuerelemente können nur gehostet werden, wenn der Client Computer über die richtige Lizenz verfügt.

## <a name="see-also"></a>Siehe auch

[ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)
