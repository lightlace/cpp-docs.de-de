---
title: MFC-ActiveX-Steuerelement-Assistent
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: 009c7a2b0c703facf70b7a4b2706f288c4d7fd9a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267580"
---
# <a name="mfc-activex-control-wizard"></a>MFC-ActiveX-Steuerelement-Assistent

Ein ActiveX-Steuerelement ist ein spezieller Typ einer [Automatisierungsserver](../../mfc/automation-servers.md); es ist eine wiederverwendbare Komponente. Die Anwendung hosten des ActiveX-Steuerelements ist die [Automatisierungsclient](../../mfc/automation-clients.md) des Steuerelements. Wenn Ihr Ziel ist eine wieder verwendbare Komponente erstellen, verwenden Sie diesen Assistenten, um das Steuerelement zu erstellen. Finden Sie unter [MFC-ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md) für Weitere Informationen.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](../activex-controls.md).

Alternativ können Sie erstellen, ein Automation Server MFC-Anwendung mit der [MFS-Anwendungsassistenten](../../mfc/reference/mfc-application-wizard.md).

Ein ActiveX-Steuerelement mit diesem Assistenten erstellen, kann über eine Benutzeroberfläche verfügen oder unsichtbar sein. Sie können mit dieser Option angeben der [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite des Assistenten. Ein Zeitgeber-Steuerelement ist ein Beispiel für ein ActiveX-Steuerelement, das nicht sichtbar sein sollen.

ActiveX-Steuerelemente können eine komplexen Benutzeroberfläche verwenden. Einige Steuerelemente wie gekapselten Formulare werden können: ein einzelnes Steuerelement mit vielen Felder, von denen jede ein eigenes Windows-Steuerelement. Beispielsweise kann ein Auto-Teile-Objekt als ein MFC-ActiveX-Steuerelement implementiert eine Formular-ähnliche-Benutzeroberfläche anzeigen, Benutzer können über der lesen und bearbeiten, die Teilenummer, Teilen und andere Informationen. Finden Sie unter [MFC-ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md) für Weitere Informationen.

Wenn Sie einen Container für ActiveX-Objekte erstellen möchten, finden Sie unter [erstellen Sie einen ActiveX-Steuerelementcontainer](../../mfc/reference/creating-an-mfc-activex-control-container.md).

Die MFC-Startprogramm enthält C++-Quelldateien (.cpp), Ressourcendateien (.rc) und eine Projektdatei (.vcxproj). In diesen Startdateien generierte Code basiert auf MFC.

Die folgende Beispielliste enthält Aufgaben und Typen von Erweiterungen für ActiveX-Steuerelement:

- [Optimieren der ActiveX-Steuerelement](../../mfc/mfc-activex-controls-optimization.md)

- [Hinzufügen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Hinzufügen von benutzerdefinierten Ereignissen](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [Hinzufügen von vordefinierten Methoden](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [Hinzufügen von benutzerdefinierten Methoden](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [Hinzufügen von vordefinierten Eigenschaften](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Hinzufügen von benutzerdefinierten Eigenschaften](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>Übersicht

Diese Seite des Assistenten wird beschrieben, die aktuellen Einstellungen für die MFC-ActiveX-Steuerelement, die Sie erstellen. Der Assistent erstellt ein Projekt standardmäßig wie folgt:

- Das Standardprojekt generiert keine Laufzeit-Lizenz oder Hilfe-Dateien. Sie können diese Standardeinstellungen ändern, auf die [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) Seite. Nur die Auswahl, die Sie, auf dieser Seite des ActiveX-Steuerelement-Assistenten vornehmen werden übernommen, auf die **Übersicht** Seite.

- Das Projekt enthält eine Steuerelementklasse und eine Eigenschaftenseitenklasse, die basierend auf den Namen des Projekts. Sie können den Namen der Ihr Projekt und die Datei bearbeiten, auf die [Steuerelementnamen](../../mfc/reference/control-names-mfc-activex-control-wizard.md) Seite.

- Das Steuerelement wird basierend auf keine vorhandenen Windows-Steuerelement, aktiviert wird, wenn es sichtbar wird, verfügt über eine Benutzeroberfläche und enthält eine **zu** Dialogfeld. Sie können diese Standardeinstellungen ändern, auf die [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwalten von Visual C++-Projekten](../../ide/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)<br/>
[Konzepte](../../atl/active-template-library-atl-concepts.md)
