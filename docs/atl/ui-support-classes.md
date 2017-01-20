---
title: "UI Support Classes"
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
  - "vc.atl.ui"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzeroberflächen, ATL-Klassen"
  - "Benutzeroberflächen, support classes"
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# UI Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen bieten allgemeine die Benutzeroberflächenunterstützung:  
  
-   [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle zum Analyse\- und Renderingmodul Microsoft HTML.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) stellt die wichtigsten Methoden, durch die ein Container ein Steuerelement ist.  Verwaltet das Einschalten und Ausschalten direkter Steuerelemente.  
  
-   [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) verwaltet die Reaktivierung von direkten Steuerelemente.  Ermöglicht einem fensterloses Steuerelement, um Nachrichten zu empfangen und an den Drag & Drop\-Operationen teilnehmen.  
  
-   [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) hilft Kommunikation zwischen einem direkten Steuerelement und dessen Container.  
  
-   [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) kann ein Steuerelement, sich direkt anzuzeigen und den Container von Änderungen in der Anzeige zu benachrichtigen.  Bietet Unterstützung für flimmerfreie Zeichnungen, nicht rechteckige und transparente Steuerelemente und Treffertests.  
  
## Verwandte Elemente  
 [ATL\-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
  
## Siehe auch  
 [Class Overview](../atl/atl-class-overview.md)