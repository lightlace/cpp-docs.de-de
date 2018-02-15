---
title: "UI-Unterstützungsklassen (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.atl.ui
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4b708dec433c120ddd8a938eadb3577a1a6d0f8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ui-support-classes"></a>Benutzeroberflächenklassen-Unterstützung
Die folgenden Klassen bieten allgemeine Benutzeroberflächenautomatisierungs-Unterstützung:  
  
-   [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle für das Microsoft HTML zu analysieren und Renderingmodul.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) Hauptmethoden, die über den ein Container kommuniziert mit einem Steuerelement enthält. Verwaltet die Aktivierung und Deaktivierung von direkten-Steuerelementen.  
  
-   [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) verwaltet die Reaktivierung von direkten Steuerelemente. Aktiviert ein fensterloses Steuerelement zum Empfangen von Nachrichten sowie bei Drag & Drop-Vorgängen teilnehmen.  
  
-   [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) unterstützt die Kommunikation zwischen einer direkten-Steuerelement und dessen Container.  
  
-   [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) ermöglicht es einem Steuerelement selbst nicht direkt anzeigen und den Container der Änderungen in der Anzeige zu benachrichtigen. Bietet Unterstützung für flimmerfreier zeichnen, viereckig noch transparent Steuerelemente und Treffertests.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../atl/atl-class-overview.md)

