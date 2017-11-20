---
title: "Objekte und Steuerelemente hinzufügen, eine ATL-Projekt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.controls
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e01b39eb7393d171b2c1fb30193810f62be85b99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt
Sie können eines ATL-Code-Assistenten verwenden, auf ein Objekt oder ein Steuerelement zu ATL und MFC-basierten Projekten hinzufügen. Für jedes COM-Objekt oder ein Steuerelement hinzufügen Sie, generiert der Assistent cpp und h-Dateien als auch eine RGS-Datei für die Registrierung skriptbasierte-Unterstützung. Die folgenden ATL-Code-Assistenten sind in Visual Studio verfügbar:  
  
||||  
|-|-|-|  
|[Einfaches ATL-Objekt](../../atl/reference/atl-simple-object-wizard.md)|[ATL-Dialogfeld](../../atl/reference/atl-dialog-wizard.md)|[ATL-Steuerelement](../../atl/reference/atl-control-wizard.md)|  
|[ATL-Eigenschaftenseite](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL-OLE DB-Consumers](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[ATL-Unterstützung zu MFC hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL-OLE DB-Anbieter](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  Vor dem Hinzufügen eines ATL-Objekts zu Ihrem Projekt, lesen Sie die Informationen und die Anforderungen für das Objekt in der zugehörigen Hilfethemen.  
  
### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>So fügen Sie ein Objekt oder ein Steuerelement mit der ATL-Steuerelement-Assistenten hinzu  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste des Projektknotens, und klicken Sie auf **hinzufügen** aus dem Kontextmenü. Klicken Sie auf **Klasse hinzufügen**.  
  
     Die [Klasse hinzufügen](../../ide/add-class-dialog-box.md) Dialogfeld wird angezeigt.  
  
2.  Wählen Sie mit dem ATL-Ordner im Bereich "Kategorien" ausgewählt wird ein Objekt, klicken Sie im Bereich "Vorlagen" eingefügt werden. Klicken Sie auf **öffnen**. Der Code-Assistenten für das ausgewählte Objekt angezeigt wird.  
  
    > [!NOTE]
    >  Wenn Sie eine ATL-Objekt zu einem MFC-Projekt hinzufügen möchten, müssen Sie dem vorhandenen Projekt ATL-Unterstützung hinzufügen. Hierzu können Sie anhand der Anweisungen in [Hinzufügen von ATL-Unterstützung auf MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
     Klicken Sie alternativ, fordert Visual Studio, wenn Sie versuchen, eine ATL-Objekt zu einem MFC-Projekt hinzufügen, ohne zuvor die ATL-Unterstützung hinzufügen, Sie angeben, ob das ATL-Unterstützung, die dem Projekt hinzugefügt werden soll. Klicken Sie auf **Ja** ATL-Unterstützung zum Projekt hinzufügen und den ausgewählten ATL-Assistenten zu öffnen.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

