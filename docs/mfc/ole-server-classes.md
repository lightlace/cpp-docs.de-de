---
title: OLE-Server-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 99dd7f58b862fadc86ee2515bb8ef2008bc538fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385322"
---
# <a name="ole-server-classes"></a>OLE-Server-Klassen

Diese Klassen werden von Server-Anwendungen verwendet. Serverdokumente davon abgeleitet sind `COleServerDoc` anstatt von `CDocument`. Beachten Sie, dass `COleServerDoc` ergibt sich aus `COleLinkingDoc`, Serverdokumente können auch sein, Container, die Verknüpfung zu unterstützen.

Die `COleServerItem` Klasse darstellt, ein Dokument oder einen Teil eines Dokuments, die in einem anderen Dokument eingebettet oder verknüpft werden kann.

`COleIPFrameWnd` und `COleResizeBar` unterstützen die direkte Bearbeitung, während das Objekt in einem Container befindet und `COleTemplateServer` unterstützt die Erstellung von Dokument/Ansicht-Paaren damit OLE-Objekte aus anderen Anwendungen, die bearbeitet werden können.

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
Als die Basisklasse verwendet für Serveranwendung Document-Klassen. `COleServerDoc` Objekte stellen den größten Teil der Unterstützung durch Interaktionen mit Server `COleServerItem` Objekte. Visual Bearbeitungsfunktionen unter Verwendung der Klassenbibliothek Dokument-/Ansichtarchitektur bereitgestellt.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
Abstrakte Basisklasse von `COleClientItem` und `COleServerItem`. Objekte der Klassen abgeleitet `CDocItem` Teilen von Dokumenten darstellen.

[COleServerItem](../mfc/reference/coleserveritem-class.md)<br/>
Verwendet, um die OLE-Schnittstelle, um darzustellen `COleServerDoc` Elemente. Es ist in der Regel eine `COleServerDoc` -Objekt, das den eingebetteten Teil eines Dokuments darstellt. In der Server, die Links zu den Teilen von Dokumenten zu unterstützen, sind viele `COleServerItem` Objekte, von denen jedes einen Link auf einen Teil des Dokuments darstellt.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Stellt das Rahmenfenster für eine Sicht, wenn Serverdokument direkt bearbeitet wird.

[COleResizeBar](../mfc/reference/coleresizebar-class.md)<br/>
Stellt die Standardbenutzeroberfläche für direkte größenänderungen. Objekte dieser Klasse werden immer in Verbindung mit verwendet `COleIPFrameWnd` Objekte.

[COleTemplateServer](../mfc/reference/coletemplateserver-class.md)<br/>
Zum Erstellen von Dokumenten mithilfe des Frameworks Dokument-/Ansichtarchitektur verwendet. Ein `COleTemplateServer` Objekt delegiert der Großteil der Arbeit auf ein zugeordnetes `CDocTemplate` Objekt.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Eine Ausnahme, die nach einem Fehler bei der Verarbeitung von OLE. Diese Klasse wird von sowohl Container und Server verwendet.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
