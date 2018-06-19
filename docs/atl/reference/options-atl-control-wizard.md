---
title: Optionen, ATL-Steuerelement-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab1062d32aadc2ec4af68cda8bca02ac1a45a526
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364472"
---
# <a name="options-atl-control-wizard"></a>Optionen, ATL-Steuerelement-Assistent
"Suchergebnisse" Zusammenfassung hier einfügen.  
  
 Mithilfe dieser Seite des Assistenten können Sie um den Typ des Steuerelements zu definieren, die Sie erstellen und die Ebene der Unterstützung der Schnittstelle enthält.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Steuerelementtyp**  
 Die Art des Steuerelements, das Sie erstellen möchten.  
  
-   **Standardkontrollblöcke: ein ActiveX-Steuerelement.**  
  
-   **Zusammengesetztes Steuerelement**: ein ActiveX-Steuerelement, das (ähnlich wie ein Dialogfeld) enthalten, kann andere ActiveX-Steuerelemente oder Windows-Steuerelemente. Ein zusammengesetztes Steuerelement umfasst Folgendes:  
  
    -   Eine Vorlage für das Dialogfeld, das die zusammengesetzten Steuerelements implementiert.  
  
    -   Eine benutzerdefinierte Ressource, Registrierung, die den zusammengesetzten Steuerelements beim Aufrufen automatisch registriert.  
  
    -   Eine C++-Klasse, die zusammengesetzten Steuerelements implementiert.  
  
    -   Eine COM-Schnittstelle, die von zusammengesetzten Steuerelementen verfügbar gemacht werden.  
  
    -   Die zusammengesetzten Steuerelements mit HTML-Testseite.  
  
     Standardmäßig legt das Steuerelement [CComControlBase](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) auf "true", um anzugeben, dass dies ein Steuerelement mit Fenster ist. Eine Karte Senke implementiert. Weitere Informationen finden Sie unter [Unterstützung für DHTML-Steuerelemente](../../atl/atl-support-for-dhtml-controls.md).  
  
-   **DHTML-Steuerelemente**: ein ATL-DHTML-Steuerelement gibt an, die Benutzeroberfläche mit HTML. DHTML-UI-Klasse enthält eine COM-Zuordnung. Standardmäßig legt das Steuerelement [CComControlBase](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) auf "true", um anzugeben, dass dies ein Steuerelement mit Fenster ist.  
  
     Weitere Informationen finden Sie unter [identifizieren die Elemente eines DHTML-Steuerelementprojekts](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
 **Nur minimale Kontrolle**  
 Unterstützt nur die Schnittstellen, die von den meisten Containern absolut erforderlich sind. Sie können festlegen, **nur minimale Kontrolle** für alle Steuerelementtypen angezeigt: Sie können ein minimal standard-Steuerelement, ein minimaler zusammengesetztes Steuerelement oder ein minimal DHTML-Steuerelement erstellen.  
  
 **Aggregation**  
 Fügt Unterstützung für das Steuerelement, das Sie erstellen. Weitere Informationen finden Sie unter [Aggregation](../../atl/aggregation.md).  
  
-   **Ja**: Erstellen eines Steuerelements, die aggregiert werden können.  
  
-   **Nicht**: Erstellen Sie ein Steuerelement, das nicht aggregiert werden kann.  
  
-   **Nur**: Erstellen Sie ein Steuerelement, das nur durch die Aggregation instanziiert werden kann.  
  
 **Threadmodell**  
 Gibt an, dass das Threadingmodell vom Steuerelement verwendet.  
  
-   **Einzelne**: das Steuerelement wird nur im primären COM-Thread ausgeführt.  
  
-   **Apartment**: das Steuerelement kann in jeder einzelnen Thread-Apartment erstellt werden. Der Standardwert.  
  
 **Interface**  
 Der Typ der Schnittstelle macht dieses Steuerelement auf den Container.  
  
-   **Duale**: erstellt eine Schnittstelle, die Eigenschaften und Methoden über macht `IDispatch` und direkt durch die VTBL.  
  
-   **Benutzerdefinierte**: erstellt eine Schnittstelle, die Methoden direkt durch eine VTBL verfügbar macht.  
  
     Bei Auswahl des **benutzerdefinierte**, können Sie angeben, dass das Steuerelement ist **Automatisierungskompatibel**. Bei Auswahl des **Automatisierungskompatibel**, fügt der Assistent die [Oleautomation](../../windows/oleautomation.md) -Attribut auf die Schnittstelle in der IDL-Datei, und die Schnittstelle vom universal Marshaller in oleaut32.dll gemarshallt werden kann. Finden Sie unter [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621) in das Windows SDK für Weitere Informationen.  
  
     Darüber hinaus bei Auswahl des **Automatisierungskompatibel**, und klicken Sie dann alle Parameter für alle Methoden des Steuerelements Transportservers **VARIANT** kompatibel.  
  
 **Unterstützung**  
 Legt zusätzliche sonstige Unterstützung für das Steuerelement fest.  
  
-   **Verbindungspunkte**: Aktiviert Verbindungspunkte für das Objekt, indem Sie machen die Klasse des Objekts abgeleitet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) und ermöglicht eine Quellschnittstelle verfügbar zu machen.  
  
-   **Lizenziert**: Fügt Unterstützung für das Steuerelement für [Lizenzierung](http://msdn.microsoft.com/library/windows/desktop/ms690543). Lizenzierte Steuerelemente können nur gehostet werden, wenn der Clientcomputer die richtige Lizenz verfügt.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md)

