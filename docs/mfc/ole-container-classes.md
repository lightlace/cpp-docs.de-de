---
title: OLE-Containerklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df809971ecf8bdd8700217cf6a1965e2973de754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ole-container-classes"></a>OLE-Containerklassen
Diese Klassen werden von containeranwendungen verwendet. Beide `COleLinkingDoc` und `COleDocument` Verwalten von Sammlungen `COleClientItem` Objekte. Anstatt das Ableiten einer Dokumentklasse aus **CDocument**, leiten Sie ihn von `COleLinkingDoc` oder `COleDocument`, je nachdem, ob Sie Unterstützung wünschen, Links zu den in Ihr Dokument eingebettete Objekte.  
  
 Verwenden einer `COleClientItem` Objekt, das jeden OLE-Element im Dokument darstellen, die aus einem anderen Dokument eingebettet ist oder einen Link zu einem anderen Dokument ist.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 Active Document-Container wird unterstützt.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Für Verbunddokumente Implementierung als auch grundlegende containerunterstützung verwendet. Dient als Container für Klassen abgeleitet `CDocItem`. Diese Klasse kann als Basisklasse verwendet werden, für Container dokumentiert und die Basisklasse für ist `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Eine abgeleitete Klasse `COleDocument` , der die Infrastruktur für das Verknüpfen von bereitstellt. Sie sollten die Document-Klassen ableiten, für die containeranwendungen von dieser Klasse anstelle von `COleDocument` , wenn Sie Links zu eingebetteten Objekte unterstützen sollen.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Verwaltet die Liste der OLE-Client-Elemente, die im rich-Edit-Steuerelement. Mit verwendet [CRichEditView](../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Abstrakte Basisklasse von `COleClientItem` und `COleServerItem`. Objekte der Klassen abgeleitet `CDocItem` Dokumentteilen darstellen.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 Eine Client-Element-Klasse, die Clientseite der Verbindung mit einem eingebettete oder verknüpfte OLE-Element darstellt. Ihre Clientelemente werden von dieser Klasse ableiten.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Ermöglicht die clientseitige Zugriff auf ein Element in einem rich-Edit-Steuerelement bei Verwendung mit gespeicherten OLE `CRichEditView` und `CRichEditDoc`.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Eine Ausnahme, die resultierenden nach einem Fehler bei der OLE-Verarbeitung. Diese Klasse wird von Container und Server.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

