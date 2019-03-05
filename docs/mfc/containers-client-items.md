---
title: 'Container: Clientelemente'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: 0c7f4a63cb9a31b52be2d3574ddad29313df6a4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298281"
---
# <a name="containers-client-items"></a>Container: Clientelemente

In diesem Artikel wird erläutert, welche Clientelemente sind und von welchen Klassen Ihrer Anwendung sollten die Clientelemente ableiten.

Clientelemente sind Datenobjekte, die auf eine andere Anwendung, die entweder innerhalb oder auf eine OLE-Container-Anwendung Dokument verweist, gehören. Clientelemente, deren Daten im Dokument enthalten ist, werden eingebettet; diejenigen, deren Daten in einen anderen Speicherort, auf die verwiesen wird durch das Containerdokument gespeichert werden, verknüpft sind.

Document-Klasse in einer OLE-Anwendung wird von der Klasse abgeleitet [COleDocument](../mfc/reference/coledocument-class.md) anstatt von `CDocument`. Die `COleDocument` Klasse erbt von `CDocument` alle Funktionen, die für die Verwendung der Anwendungen auf der MFC basieren Dokument-/Ansichtarchitektur erforderlich. `COleDocument` Außerdem definiert eine Schnittstelle, die ein Dokument als eine Auflistung von behandelt `CDocItem` Objekte. Mehrere `COleDocument` Memberfunktionen zum Hinzufügen, abrufen und Löschen von Elementen, die dieser Sammlung bereitgestellt werden.

Jeder containeranwendung sollte über mindestens eine Klasse von ableiten `COleClientItem`. Objekte dieser Klasse stellen die Elemente, die eingebettete oder verknüpfte im OLE-Dokument dar. Diese Objekte vorhanden für die Lebensdauer des Dokuments, enthält sie, es sei denn, sie aus dem Dokument gelöscht werden.

`CDocItem` ist die Basisklasse für `COleClientItem` und `COleServerItem`. Objekte der Klassen, die von diesen beiden fungieren als Vermittler zwischen der OLE-Element und die Client- und serveranwendungen. Jedes Mal ein neues OLE-Element, auf das Dokument hinzugefügt wird, das MFC-Framework Fügt ein neues Objekt Ihrer Clientanwendung `COleClientItem`-abgeleiteten Klasse auf das Dokument in der Auflistung von `CDocItem` Objekte.

## <a name="see-also"></a>Siehe auch

[Container](../mfc/containers.md)<br/>
[Container: Verbunddateien](../mfc/containers-compound-files.md)<br/>
[Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md)<br/>
[Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md)<br/>
[COleClientItem-Klasse](../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem-Klasse](../mfc/reference/coleserveritem-class.md)
