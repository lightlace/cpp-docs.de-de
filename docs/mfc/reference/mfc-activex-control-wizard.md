---
title: MFC-ActiveX-Steuerelement-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45af43a98244e90f52075817fc9e17a905cbf065
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-control-wizard"></a>MFC-ActiveX-Steuerelement-Assistent
Ein ActiveX-Steuerelement ist ein spezieller Typ einer [Automatisierungsservers](../../mfc/automation-servers.md); es ist eine wiederverwendbare Komponente sein. Die Anwendung, die ActiveX-Steuerelement ist die [Automatisierungsclient](../../mfc/automation-clients.md) dieses Steuerelements. Wenn Ihr Ziel ist eine solche wiederverwendbare Komponente zu erstellen, verwenden Sie diesen Assistenten, um das Steuerelement zu erstellen. Finden Sie unter [MFC-ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md) für Weitere Informationen.  
  
 Alternativ können Sie erstellen, eine Automatisierung Server MFC-Anwendung mit der [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md).  
  
 Mit diesem Assistenten erstellte ActiveX-Steuerelement kann über eine Benutzeroberfläche verfügen oder unsichtbar sein. Sie können angeben, dass diese Option in der [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite des Assistenten. Ein Zeitgeber-Steuerelement ist ein Beispiel für ein ActiveX-Steuerelement, das Sie nicht sichtbar sein soll.  
  
 ActiveX-Steuerelemente können eine komplexe Benutzeroberfläche haben. Einige Steuerelemente wie gekapselte Formulare möglicherweise: ein einzelnes Steuerelement mit vielen Feldern, von denen jedes ein Windows-Steuerelement vollkommen. Beispielsweise kann ein Auto Teile-Objekt als ein MFC-ActiveX-Steuerelement implementiert eine Formular-ähnliche Benutzeroberfläche vorhanden, durch die Benutzer zu lesen und bearbeiten die Teilenummer, mehrteiligen Namen und andere Informationen konnte. Finden Sie unter [MFC-ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md) für Weitere Informationen.  
  
 Wenn Sie einen Container für ActiveX-Objekte erstellen möchten, finden Sie unter [Erstellen eines ActiveX-Steuerelementcontainers](../../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
 Das MFC-Startprogramm enthält C++-Quelldateien (.cpp), Ressourcendateien (.rc) und eine Projektdatei (.vcxproj). In diesen Startdateien generierte Code basiert auf MFC.  
  
 Das folgende Beispielliste enthält Aufgaben und Typen von Erweiterungen für ActiveX-Steuerelements:  
  
-   [Optimieren der ActiveX-Steuerelement](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [Hinzufügen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Hinzufügen von benutzerdefinierten Ereignissen](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [Hinzufügen von vordefinierten Methoden](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Hinzufügen von benutzerdefinierten Methoden](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Hinzufügen von vordefinierten Eigenschaften](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Hinzufügen von benutzerdefinierten Eigenschaften](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## <a name="overview"></a>Übersicht  
 Diese Seite des Assistenten wird beschrieben, die aktuellen Anwendungseinstellungen für das MFC-ActiveX-Steuerelement-Projekt, das Sie erstellen. Der Assistent erstellt ein Projekt standardmäßig wie folgt:  
  
-   Das Standardprojekt generiert keine Dateien zur Laufzeit, Lizenz- oder -Hilfe. Sie können diese Standardeinstellungen ändern, auf die [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) Seite. Nur die Auswahl Sie treffen Sie auf dieser Seite des ActiveX-Steuerelement-Assistenten auf wiedergegeben werden die **Übersicht** Seite.  
  
-   Das Projekt enthält eine Steuerelementklasse und eine Eigenschaft Page-Klasse, basierend auf den Namen des Projekts. Sie können die Namen der Namen des Projekts und Datei bearbeiten, auf die [Steuerelementnamen](../../mfc/reference/control-names-mfc-activex-control-wizard.md) Seite.  
  
-   Das Steuerelement basiert auf keinem vorhandenen Windows-Steuerelement, aktiviert wird, wenn es sichtbar wird, verfügt über eine Benutzeroberfläche und enthält eine **zu** (Dialogfeld). Sie können diese Standardeinstellungen ändern, auf die [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwalten von Visual C++-Projekten](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Konzepte](../../atl/active-template-library-atl-concepts.md)

