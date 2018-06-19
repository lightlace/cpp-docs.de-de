---
title: Dokumentieren Sie Klassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2073e432dd0d0792e358a3f159892aea405197c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346616"
---
# <a name="document-classes"></a>Dokumentklassen
Dokument-Klassenobjekten, erstellt von Dokumentvorlagen-Objekten, Verwalten der Anwendungsdaten verwendet werden. Eine Klasse wird für die Dokumente aus einer dieser Klassen abgeleitet werden.  
  
 -Klasse Dokumentobjekte interagieren Objekte anzeigen. Anzeigen von Objekten der Clientbereich eines Fensters darstellen, Anzeigen von Daten eines Dokuments und ermöglichen Benutzern die Interaktion mit. Dokumente und Ansichten werden von einem Dokument-Template-Objekt erstellt.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 Die Basisklasse für anwendungsspezifische Dokumente. Leiten Sie Ihre Dokumentklasse oder Klassen von **CDocument**.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Für Verbunddokumente Implementierung als auch grundlegende containerunterstützung verwendet. Dient als Container für Klassen abgeleitet [CDocItem](../mfc/reference/cdocitem-class.md). Diese Klasse kann als Basisklasse verwendet werden, für Container dokumentiert und die Basisklasse für ist `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Eine abgeleitete Klasse `COleDocument` , der die Infrastruktur für das Verknüpfen von bereitstellt. Sie sollten die Document-Klassen ableiten, für die containeranwendungen von dieser Klasse anstelle von `COleDocument` , wenn Sie Links zu eingebetteten Objekte unterstützen sollen.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Verwaltet die Liste der OLE-Client-Elemente, die im rich-Edit-Steuerelement. Mit verwendet [CRichEditView](../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Als Basisklasse verwendet für Server-Anwendung Document-Klassen. `COleServerDoc` -Objekte stellen den Großteil serverunterstützung durch Interaktionen mit [COleServerItem](../mfc/reference/coleserveritem-class.md) Objekte. Verwendung der Klassenbibliothek Dokument-/Ansichtarchitektur Visual Bearbeitungsfunktionen bereitgestellt.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Bereitstellt, mit [CHtmlEditView](../mfc/reference/chtmleditview-class.md), die Funktionalität der WebBrowser HTML-Bearbeitungsplattform im Rahmen der MFC-Dokument-/ Ansichtsarchitektur.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 -Klasse Dokumentobjekte dauerhaft sein können – das heißt, sie es wieder zu lesen und Schreiben von ihren Status auf einem Speichermedium können. MFC stellt die `CArchive` Klasse, um zu ermöglichen, die Daten des Dokuments auf einem Speichermedium übertragen.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 Arbeitet mit einem [CFile](../mfc/reference/cfile-class.md) Objekt permanenten Speicher für Objekte, die über die Serialisierung implementiert (finden Sie unter [Einfügeoperatoren](../mfc/reference/cobject-class.md#serialize)).  
  
 Dokumente können auch OLE-Objekte enthalten. `CDocItem` ist die Basisklasse der Server- und Client-Elemente.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Abstrakte Basisklasse von [COleClientItem](../mfc/reference/coleclientitem-class.md) und [COleServerItem](../mfc/reference/coleserveritem-class.md). Objekte der Klassen abgeleitet `CDocItem` Dokumentteilen darstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

