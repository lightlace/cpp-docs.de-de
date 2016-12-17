---
title: "Verwenden von CAnimateCtrl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Animationssteuerungselemente [C++], CAnimateCtrl-Klasse"
  - "CAnimateCtrl-Klasse, Informationen über CAnimateCtrl-Klasse"
  - "Steuerelemente [MFC], Animation"
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von CAnimateCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Animationssteuerung, dargestellt durch die [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), ist ein Fenster, das einen Klipp 3.00\-Format Audio\- Video Interleaveds \(AVI\) \- das Standard\-Windows\-Video\/das Audioformat anzeigt.  Ein AVI\-Klipp ist Reihe Bitmapframes, wie ein Film.  
  
 Wenn der Thread die Ausführung fortsetzt, während der AVI\-Klipp angezeigt wird, wird eine allgemeine Verwendung für ein Animationssteuerung, Systemaktivität während eines längeren Vorgangs angegeben.  Beispielsweise zeigt das Windows\-Suchendialogfeld verschiebbar Lupe als die Systemsuchen für eine Datei an.  
  
 Animationssteuerelemente können einfache AVI\-Klipps nur wiedergeben, und sie unterstützen nicht wiedergegeben. \(Eine vollständige Liste der Einschränkungen, finden Sie unter [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).\) Da die Funktionen eines Animationssteuerelements Strict und ändern beschränkt werden, sollten Sie eine Alternative wie das MCIWnd\-Steuerelement verwenden, wenn Sie ein Steuerelement benötigen, um Multimediaplayback\- und\/oder \-Aufzeichnungsfunktionen bereitzustellen.  Weitere Informationen zum MCIWnd\-Steuerelement, finden Sie die Multimediadokumentation.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden eines Animationssteuerelements](../mfc/using-an-animation-control.md)  
  
-   [Benachrichtigungen gesendet durch Animationssteuerelemente](../mfc/notifications-sent-by-animation-controls.md)  
  
## Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)