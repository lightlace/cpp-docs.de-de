---
title: OLE-Hintergrund | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c0de0bf2b20f4bdb2d1103154f1ba311fc7134
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443831"
---
# <a name="ole-background"></a>OLE-Hintergrund

OLE wird ein Mechanismus, mit der Benutzer zum Erstellen und Bearbeiten der Dokumente, die Elemente oder "Objekte" von mehreren Anwendungen erstellt.

> [!NOTE]
>  OLE war ursprünglich ein Akronym für Object Linking and Embedding. Allerdings ist es nun als OLE bezeichnet. Teile von OLE, die nicht im Zusammenhang mit verlinken und Einbetten sind jetzt Teil der Active-Technologie.

OLE-Dokumente, die in der Vergangenheit namens Verbunddokumente, lassen sich verschiedene Arten von Daten oder Komponenten nahtlos integrieren. Soundclips, Kalkulationstabellen und Bitmaps sind typische Beispiele für Komponenten im OLE-Dokumente. Unterstützung von OLE in Ihrer Anwendung kann Ihre Benutzer auf die OLE-Dokumente verwenden, ohne sich Gedanken, zwischen den verschiedenen Anwendungen wechseln; OLE erledigt für Sie.

Verwenden Sie eine Container-Anwendung zum Erstellen von zusammengesetzter Dokumenten und eine Server-Anwendung oder Komponente-Anwendung, um die Elemente innerhalb des Containerdokuments zu erstellen. Jede Anwendung, die Sie schreiben, kann es sich um einen Container, einen Server oder beides sein.

OLE umfasst viele verschiedene Konzepte, dass alle für das Ziel der nahtlose Interaktion zwischen Anwendungen funktionieren. Diese Bereiche umfassen Folgendes:

- Verlinken und einbetten

   Verlinken und Einbetten sind die beiden Methoden zum Speichern von Elementen, die in ein OLE-Dokument erstellt, die in einer anderen Anwendung erstellt wurden. Allgemeine Informationen zu den Unterschieden zwischen den beiden finden Sie im Artikel [OLE-Hintergrund: verlinken und einbetten](../mfc/ole-background-linking-and-embedding.md). Weitere Informationen finden Sie unter den Artikeln [Container](../mfc/containers.md) und [Server](../mfc/servers.md).

- Direkte Aktivierung (visuelle Bearbeitung)

   Aktivieren ein eingebettetes Element im Kontext des Containerdokuments wird die direkte Aktivierung oder die visuelle Bearbeitung aufgerufen werden. Die Container-Anwendung-Schnittstelle ändert, um die Funktionen von der Komponente-Anwendung zu integrieren, die das eingebettete Element erstellt. Verknüpfte Elemente werden nie vorhanden aktiviert, da die tatsächlichen Daten für das Element in einer separaten Datei, aus dem Kontext der Anwendung mit dem Link enthalten ist. Weitere Informationen zum direkten Aktivierung, finden Sie im Artikel [Aktivierung](../mfc/activation-cpp.md).

   > [!NOTE]
   > Verlinken und einbetten und direkte Aktivierung geben Sie die wichtigsten Funktionen der OLE-visual-Bearbeitung.

- Automation-Automatisierung ermöglicht einer Anwendung in einer anderen Anwendung steuern. Die treibende Anwendung wird als ein Automatisierungsclient bezeichnet, und die Anwendung gesteuert wird, wird als Automatisierungsserver oder Automatisierungskomponente bezeichnet. Weitere Informationen zu Automation finden Sie in den Artikeln [Automatisierungsclients](../mfc/automation-clients.md) und [Automatisierungsserver](../mfc/automation-servers.md).

   > [!NOTE]
   > Automation arbeitet sowohl aktive als auch OLE-Technologie-Kontexte. Sie können ein Objekt, das basierend auf COM automatisieren.

- Verbunddateien

   Compound-Dateien geben Sie ein standard-Dateiformat, das den strukturierten Speicherung von zusammengesetzten Dokumenten für OLE-Anwendungen vereinfacht. In einer Verbunddatei Speicher über viele Features der Verzeichnisse und Streams verfügen über viele Funktionen von Dateien aus. Diese Technologie wird auch strukturierten Speicher bezeichnet. Weitere Informationen zu compound-Dateien, finden Sie im Artikel [Container: Verbunddateien](../mfc/containers-compound-files.md).

- Einheitliche Datenübertragung

   Uniform Data Transfer (UDT) ist ein Satz von Schnittstellen, mit die Daten gesendet und empfangen in eine standardmäßige Art und Weise, unabhängig von der tatsächlichen Methode zum Übertragen von Daten ausgewählt werden können. UDT-Formulare, denen die Grundlage für die Daten von überträgt ziehen und ablegen. UDT ist jetzt als Basis für eine vorhandene Windows-Datenübertragung, z. B. in die Zwischenablage und dynamischer Datenaustausch (DDE). Weitere Informationen zu UDTS, finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md).

- Drag & Drop

   Drag & Drop ist eine einfach zu bedienende, Direct-Manipulation Technik zum Übertragen von Daten zwischen Anwendungen, die unter Windows in einer Anwendung oder sogar in ein einzelnes Fenster in einer Anwendung. Der zu übertragenden Daten ausgewählt und auf das gewünschte Ziel gezogen wird. Drag & Drop basiert auf einheitliche Datenübertragung. Weitere Informationen zu Drag & Drop, finden Sie im Artikel [Drag & Drop](../mfc/drag-and-drop-ole.md).

- Component Object Model

   Das Component Object Model (COM) bietet die Infrastruktur verwendet, wenn OLE-Objekte miteinander kommunizieren. Die MFC-OLE-Klassen vereinfachen die COM-Programmierer. COM ist Teil der Active-Technologie, da COM-Objekte OLE und aktive Technologie zugrunde liegen. Weitere Informationen zu COM, finden Sie unter den [Active Template Library (ATL)](../atl/active-template-library-atl-concepts.md) Themen.

Einige der wichtigeren OLE Themen werden in den folgenden Artikeln behandelt:

- [OLE-Hintergrund: Verlinken und Einbetten](../mfc/ole-background-linking-and-embedding.md)

- [OLE-Hintergrund: Container und Server](../mfc/ole-background-containers-and-servers.md)

- [OLE-Hintergrund: Implementierungsstrategien](../mfc/ole-background-implementation-strategies.md)

- [OLE-Hintergrund: MFC-Implementierung](../mfc/ole-background-mfc-implementation.md)

Allgemeine OLE-Informationen, die in der oben genannten Artikel nicht gefunden suchen Sie nach OLE in MSDN.

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)

