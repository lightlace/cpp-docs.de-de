---
title: Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.controls
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e70ac6f333312fc62854478897912fc28f3c2f8e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756560"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt

Sie können eines der ATL-Code-Assistenten verwenden, ein Objekt oder ein Steuerelement zu ATL oder MFC-basierten Projekten hinzufügen. Für jede COM-Objekt oder ein Steuerelement hinzufügen Sie, generiert der Assistent cpp- und .h-Dateien als auch ein RGS-Datei für die Unterstützung für skriptbasierte Registrierung. Die folgenden ATL-Code-Assistenten stehen in Visual Studio zur Verfügung:

||||
|-|-|-|
|[ATL Simple Object (Einfaches ATL-Objekt)](../../atl/reference/atl-simple-object-wizard.md)|[ATL-Dialogfeld](../../atl/reference/atl-dialog-wizard.md)|[ATL-Steuerelement](../../atl/reference/atl-control-wizard.md)|
|[ATL-Eigenschaftenseite](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page-Komponente](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL-OLE DB-Consumers](../../atl/reference/atl-ole-db-consumer-wizard.md)|
|[ATL-Unterstützung zu MFC hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL-OLE DB-Anbieter](../../atl/reference/atl-ole-db-provider-wizard.md)|

> [!NOTE]
> Bevor ein ATL-Objekt zu Ihrem Projekt hinzufügen, sollten Sie die Informationen und die Anforderungen für das Objekt in seine Verwandte Hilfethemen überprüfen.

### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Hinzufügen eines Objekts oder ein Steuerelement unter Verwendung der ATL-Steuerelement-Assistent

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste des Projektknotens, und klicken Sie auf **hinzufügen** aus dem Kontextmenü. Klicken Sie auf **hinzufügen**.

   Die [Klasse hinzufügen](../../ide/add-class-dialog-box.md) Dialogfeld wird angezeigt.

2. Wählen Sie mit dem ATL-Ordner, in dem Bereich "Kategorien" ausgewählt ein Objekt, das im Bereich Vorlagen eingefügt. Klicken Sie auf **öffnen**. Der Code-Assistenten für das ausgewählte Objekt wird angezeigt.

   > [!NOTE]
   >  Wenn Sie ein ATL-Objekt zu einem MFC-Projekt hinzufügen möchten, müssen Sie ATL-Unterstützung dem vorhandenen Projekt hinzufügen. Hierzu können Sie die Anweisungen im [ATL-Unterstützung hinzufügen, MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).

   Klicken Sie alternativ, fordert Visual Studio, wenn Sie versuchen, ein ATL-Objekt zu einem MFC-Projekt hinzufügen, ohne zuvor die ATL-Unterstützung hinzufügen, Ihnen die Angabe, ob ATL-Unterstützung zu Ihrem Projekt hinzugefügt werden soll. Klicken Sie auf **Ja** ATL-Unterstützung zum Projekt hinzufügen und die ausgewählten ATL-Assistenten zu öffnen.

## <a name="see-also"></a>Siehe auch

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
[Visual C++ Project Types (Visual C++-Projekttypen)](../../ide/visual-cpp-project-types.md)   
[Creating Desktop Projects By Using Application Wizards (Erstellen von Desktopprojekten mit Anwendungs-Assistenten)](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
[Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

