---
title: OLE-Serverklasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d23c7cb23d9221f8f2183c666a99c70ef149db3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ole-server-classes"></a>OLE-Server-Klassen
Diese Klassen werden von serveranwendungen verwendet. Serverdokumente abgeleitet sind `COleServerDoc` anstatt von **CDocument**. Beachten Sie, dass, weil `COleServerDoc` stammt aus `COleLinkingDoc`, Serverdokumente können auch sein, Container, die Verknüpfung zu unterstützen.  
  
 Die `COleServerItem` Klasse darstellt, ein Dokument oder einen Teil eines Dokuments, die in einem anderen Dokument eingebettet oder verknüpft werden kann.  
  
 `COleIPFrameWnd`und `COleResizeBar` unterstützt direktes Bearbeiten, während das Objekt in einem Container befindet und `COleTemplateServer` unterstützt die Erstellung von Dokument-/Ansichtarchitektur Paare damit OLE-Objekte aus anderen Programmen bearbeitet werden können.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Als Basisklasse verwendet für Server-Anwendung Document-Klassen. `COleServerDoc`-Objekte stellen den Großteil serverunterstützung durch Interaktionen mit `COleServerItem` Objekte. Verwendung der Klassenbibliothek Dokument-/Ansichtarchitektur Visual Bearbeitungsfunktionen bereitgestellt.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Abstrakte Basisklasse von `COleClientItem` und `COleServerItem`. Objekte der Klassen abgeleitet `CDocItem` Dokumentteilen darstellen.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 Zur Darstellung von OLE-Schnittstelle, um `COleServerDoc` Elemente. Es ist in der Regel eine `COleServerDoc` Objekt, das die eingebetteten Teil eines Dokuments darstellt. Auf Servern, die Links zum Teilen von Dokumenten unterstützen, treten möglicherweise viele `COleServerItem` Objekte, von denen jedes einen Link zu einem Teil des Dokuments darstellt.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Stellt das Rahmenfenster für eine Sicht, wenn Serverdokument direkt bearbeitet wird.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 Stellt die Standardbenutzeroberfläche für das direkte Ändern der Größe. Objekte dieser Klasse werden immer in Verbindung mit verwendet `COleIPFrameWnd` Objekte.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 Zum Erstellen von Dokumenten mithilfe des Frameworks Dokument-/Ansichtarchitektur verwendet. Ein `COleTemplateServer` Objekt delegiert Großteil der Arbeit an einem zugeordnete `CDocTemplate` Objekt.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Eine Ausnahme, die resultierenden nach einem Fehler bei der OLE-Verarbeitung. Diese Klasse wird von Container und Server.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

