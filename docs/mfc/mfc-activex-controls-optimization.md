---
title: 'MFC-ActiveX-Steuerelemente: Optimierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4459865bc2ba374048622167fadb7bcf8fb97c99
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028173"
---
# <a name="mfc-activex-controls-optimization"></a>MFC-ActiveX-Steuerelemente: Optimierung
Dieser Artikel beschreibt die Techniken, die Sie verwenden können, um der ActiveX-Steuerelemente für eine bessere Leistung zu optimieren.  
  
 Die Themen [Aktivieren Deaktivieren der Option "aktiviert wenn sichtbar"](../mfc/turning-off-the-activate-when-visible-option.md) und [Bereitstellen der Interaktion während der Inaktivität](../mfc/providing-mouse-interaction-while-inactive.md) besprechen Sie Steuerelemente, die ein Fenster, bis Sie es aktivieren nicht erstellen. Das Thema [bereitstellen Fensterloser Aktivierung](../mfc/providing-windowless-activation.md) wird erläutert, Steuerelemente, die nie ein Fenster erstellen, selbst wenn sie aktiviert werden.  
  
 Windows haben Sie zwei wesentliche Nachteile für OLE-Objekte: sie verhindern, dass Objekte transparent oder nicht rechteckige wenn aktiv, und sie eine große Belastung der Instanziierung und die Anzeige von Steuerelementen hinzufügen. In der Regel dauert die Erstellung eines Fensters 60 Prozent der Zeitpunkt der Erstellung des Steuerelements. Mit einem gemeinsamen Fenster (in der Regel des Containers) und Verteilung Code empfängt ein Steuerelement die gleichen Fensterdienste in der Regel ohne einen Verlust der Leistung. Ein Fenster ist meist einen unnötigen Mehraufwand für das Objekt.  
  
 Einige Optimierungen sind nicht unbedingt Leistung verbessern, wenn das Steuerelement in bestimmten Containern verwendet wird. Beispielsweise hat Container vor 1996 veröffentlicht fensterlosen Aktivierung, nicht unterstützt, damit diese Funktion keinen Vorteil in älteren Container bereitstellen. Allerdings unterstützt nahezu jeder Container Persistenz, damit Optimieren Ihres Steuerelements Persistenzcode wahrscheinlich Verbessern der Leistung in jedem Container wird. Wenn das Steuerelement speziell mit der ein bestimmter Typ des Containers verwendet werden soll, sollten Sie herausfinden der dieser Optimierungen von diesem Container unterstützt wird. Im Allgemeinen sollten Sie jedoch zu implementieren, wie viele dieser Techniken wie gelten für das jeweilige Steuerelement aus, um sicherzustellen, dass das Steuerelement wie möglicherweise führt eine Vielzahl von Containern können.  
  
 Sie können viele dieser Optimierungen durch Implementieren der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md)auf die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite.  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC-ActiveX-Steuerelement-Assistent OLE-Optimierungsoptionen  
  
|Steuerelement-Einstellung in der MFC-ActiveX-Steuerelement-Assistent|Aktion|Weitere Informationen|  
|-------------------------------------------------------|------------|----------------------|  
|**Aktiviert werden, wenn sichtbar** Kontrollkästchen|Clear|[Durch das Deaktivieren der aktiviert, wenn Option "sichtbar"](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**Fensterlose Aktivierung** Kontrollkästchen|Auswählen|[Bereitstellung von fensterloser Aktivierung](../mfc/providing-windowless-activation.md)|  
|**Ungeschnittener Gerätekontext** Kontrollkästchen|Auswählen|[Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../mfc/using-an-unclipped-device-context.md)|  
|**Flimmerfreier Aktivierung** Kontrollkästchen|Auswählen|[Bereitstellen flimmerfreier Aktivierung](../mfc/providing-flicker-free-activation.md)|  
|**Mit der Maus Benachrichtigungen, wenn inaktiv** Kontrollkästchen|Auswählen|[Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**Optimierter Zeichencode** Kontrollkästchen|Auswählen|[Optimieren der Steuerelementdarstellung](../mfc/optimizing-control-drawing.md)|  
  
 Ausführliche Informationen über die Memberfunktionen, die diese Optimierungen zu implementieren, finden Sie unter [COleControl](../mfc/reference/colecontrol-class.md). Die Member-Funktionen werden durch die Verwendung aufgeführt, wie z. B. [Fensterlose Vorgänge](http://msdn.microsoft.com/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) und [Behandlungsfunktionen für inaktive Zeiger](http://msdn.microsoft.com/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Optimieren von Persistenz und Initialisierung](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [Bereitstellung von fensterloser Aktivierung](../mfc/providing-windowless-activation.md)  
  
-   [Durch das Deaktivieren der aktiviert, wenn Option "sichtbar"](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [Bereitstellen flimmerfreier Aktivierung](../mfc/providing-flicker-free-activation.md)  
  
-   [Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../mfc/using-an-unclipped-device-context.md)  
  
-   [Optimieren der Steuerelementdarstellung](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

