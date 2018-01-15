---
title: Verwenden von CAnimateCtrl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CAnimateCtrl
dev_langs: C++
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f27fd24c3c4334476c78ba0b59c90cbbb0d51f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-canimatectrl"></a>Verwenden von CAnimateCtrl
Eines Animationssteuerelements, dargestellt durch die Klasse [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), ist ein Fenster, in dem einen Clip Audio / Video Interleaved (AVI)-Format angezeigt – Windows Video-oder Audio-Standardformat. Ein AVI-Videoclips besteht aus einer Reihe von Bitmapframes, z. B. einen Film.  
  
 Da Ihr Thread ausgeführt weiterhin, während die AVI-Videoclips angezeigt wird, wird eine gemeinsame Verwendung eines Animationssteuerelements Systemaktivität während eines längeren Vorgangs angegeben. Beispielsweise zeigt das Dialogfeld Suchen Windows gleitenden Vergrößerungsglas als durchsucht eine Datei.  
  
 Animationssteuerungselemente können nur einfache AVI-Clips wiedergeben und Sound werden nicht unterstützt. (Eine vollständige Liste der Einschränkungen, finden Sie unter [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) Da die Funktionen des eines Animationssteuerelements stark eingeschränkt sind und unterliegt Änderungen sollten Sie eine Alternative wie z. B. das MCIWnd-Steuerelement verwenden, wenn Sie ein Steuerelement multimedia-Wiedergabe und/oder Aufzeichnungsfunktionen bereitstellen benötigen. Weitere Informationen über das Steuerelement MCIWnd finden Sie unter der multimedia-Dokumentation.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Verwenden eines Animationssteuerelements](../mfc/using-an-animation-control.md)  
  
-   [Von Animationssteuerelementen gesendete Benachrichtigungen](../mfc/notifications-sent-by-animation-controls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)

