---
title: 'MFC-ActiveX-Steuerelemente: Optimierung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46a17a6594db6c59148042f6e8c6cc72c7068dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-optimization"></a>MFC-ActiveX-Steuerelemente: Optimierung
Dieser Artikel beschreibt die Techniken, die Sie verwenden können, um die ActiveX-Steuerelemente für eine bessere Leistung zu optimieren.  
  
 Die Themen [deaktivieren deaktiviert die Option "aktiviert wenn sichtbar"](../mfc/turning-off-the-activate-when-visible-option.md) und [Bereitstellen der Aktivität während der Inaktivität](../mfc/providing-mouse-interaction-while-inactive.md) besprechen Sie Steuerelemente, die ein Fenster bis aktiviert nicht erstellen. Das Thema [bereitstellen Fensterloser Aktivierung](../mfc/providing-windowless-activation.md) erläutert, Steuerelemente, die nie ein Fenster erstellen, selbst wenn sie aktiviert sind.  
  
 Windows haben zwei wichtige Nachteile für OLE-Objekte: sie verhindern, dass Objekte transparent oder nicht rechteckige aktiven Zustand., und sie einen großen Aufwand für die Instanziierung und Anzeige von Steuerelementen hinzufügen. Normalerweise dauert das Erstellen eines Fensters 60 Prozent der Zeitpunkt der Erstellung des Steuerelements aus. Mit einem einzelnen freigegebenen Fenster (normalerweise des Containers) und verteilen Code erhält ein Steuerelement dieselbe Windows-Dienste, im Allgemeinen ohne Verlust der Leistung. Ein Fenster ist meist einen unnötigen Mehraufwand für das Objekt.  
  
 Einige Optimierungen sind nicht unbedingt Leistung verbessern, wenn das Steuerelement in bestimmten Container verwendet wird. Beispielsweise hat Container vor 1996 veröffentlicht fensterlosen Aktivierung, nicht unterstützt, damit diese Funktion keinen Vorteil in älteren Container bereitstellen. Allerdings unterstützt nahezu jeder Container Persistenz, Optimieren des Steuerelements Persistenzcode wahrscheinlich die Leistung in einem Container verbessert wird. Wenn das Steuerelement speziell einen bestimmten Typ von Container verwendet werden soll, können Sie untersuchen möchten der dieser Optimierungen vom Container unterstützt wird. Im Allgemeinen sollten Sie jedoch, wie viele dieser Techniken wie gelten für das jeweilige Steuerelement aus, um sicherzustellen, dass das Steuerelement möglicherweise gut wie vorgesehen führt in einer Vielzahl von Containern implementiert.  
  
 Sie können viele dieser Optimierungen durch Implementieren der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md)auf die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite.  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>OLE-Optimierungsoptionen für MFC-ActiveX-Steuerelement-Assistent  
  
|Einstellung des Steuerelements in MFC-ActiveX-Steuerelement-Assistenten|Aktion|Weitere Informationen|  
|-------------------------------------------------------|------------|----------------------|  
|**Aktivieren von sichtbaren** Kontrollkästchen|Clear|[Durch das Deaktivieren der aktiviert, wenn sichtbar-Option](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**Fensterlose Aktivierung** Kontrollkästchen|Auswählen|[Bereitstellung von fensterloser Aktivierung](../mfc/providing-windowless-activation.md)|  
|**Gerätekontexts ohne clippingbereichsanpassung** Kontrollkästchen|Auswählen|[Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../mfc/using-an-unclipped-device-context.md)|  
|**Flimmerfreier Aktivierung** Kontrollkästchen|Auswählen|[Bereitstellen flimmerfreier Aktivierung](../mfc/providing-flicker-free-activation.md)|  
|**Mit der Maus Zeiger Benachrichtigungen inaktiven Zustand** Kontrollkästchen|Auswählen|[Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**Optimierter Zeichencode** Kontrollkästchen|Auswählen|[Optimieren der Steuerelementdarstellung](../mfc/optimizing-control-drawing.md)|  
  
 Ausführliche Informationen über die Memberfunktionen, die durch diese Optimierungen implementieren, finden Sie unter [COleControl](../mfc/reference/colecontrol-class.md). Die Memberfunktionen werden nach Verwendung aufgelistet, z. B. [Fensterlose Vorgänge](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) und [inaktive Zeiger Behandlung von Funktionen](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Optimieren von Persistenz und Initialisierung](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [Bereitstellung von fensterloser Aktivierung](../mfc/providing-windowless-activation.md)  
  
-   [Durch das Deaktivieren der aktiviert, wenn sichtbar-Option](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [Bereitstellen flimmerfreier Aktivierung](../mfc/providing-flicker-free-activation.md)  
  
-   [Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../mfc/using-an-unclipped-device-context.md)  
  
-   [Optimieren der Steuerelementdarstellung](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

