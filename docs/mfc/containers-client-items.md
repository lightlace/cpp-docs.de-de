---
title: 'Container: Clientelemente | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14979f1c5f11e9a229c408e33e7c17d8776a54a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344216"
---
# <a name="containers-client-items"></a>Container: Clientelemente
In diesem Artikel wird erläutert, was Clientelemente sind und von welchen Klassen sollte die Anwendung Clientelemente ableiten.  
  
 Clientelemente sind von Datenelementen, die auf eine andere Anwendung, die entweder in enthaltenen oder verweist auf eine OLE-Container-Anwendung Dokument gehören. Clientelemente, deren Daten im Dokument enthalten ist, sind eingebettet. Rollenoptionen, deren Daten in einem anderen Speicherort verweist, die für das Containerdokument verknüpft sind.  
  
 Die Dokumentklasse in einer OLE-Anwendung wird von der Klasse abgeleitet [COleDocument](../mfc/reference/coledocument-class.md) anstatt von **CDocument**. Die `COleDocument` Klasse erbt von **CDocument** alle Funktionen für die Verwendung der Dokument-/Ansichtarchitektur Anwendungen auf MFC basieren. `COleDocument` Außerdem definiert eine Schnittstelle, die einem Dokument als eine Auflistung von behandelt `CDocItem` Objekte. Mehrere `COleDocument` Memberfunktionen zum Hinzufügen, abrufen und Löschen von Elementen, die dieser Sammlung bereitgestellt werden.  
  
 Jede Steuerelementcontainer-Anwendung sollte leiten Sie mindestens eine Klasse von `COleClientItem`. Objekte dieser Klasse stellen die Elemente, die eingebettete oder verknüpfte im OLE-Dokument dar. Für die Lebensdauer des Dokuments enthält, sind diese Objekte vorhanden, es sei denn, sie aus dem Dokument gelöscht werden.  
  
 `CDocItem` ist die Basisklasse für `COleClientItem` und `COleServerItem`. Objekte aus diesen beiden abgeleiteten Klassen dienen als Vermittler zwischen der OLE-Element und die Client- und serveranwendungen. Jedes Mal ein neues OLE-Element, auf das Dokument hinzugefügt wird, das MFC-Framework Fügt ein neues Objekt Ihrer Clientanwendung `COleClientItem`-abgeleitete Klasse auf das Dokument Auflistung von `CDocItem` Objekte.  
  
## <a name="see-also"></a>Siehe auch  
 [Containers](../mfc/containers.md)   
 [Container: Verbunddateien](../mfc/containers-compound-files.md)   
 [Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md)   
 [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md)   
 [COleClientItem-Klasse](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem-Klasse](../mfc/reference/coleserveritem-class.md)
