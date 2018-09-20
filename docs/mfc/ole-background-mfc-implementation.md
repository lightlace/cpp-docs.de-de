---
title: 'OLE-Hintergrund: MFC-Implementierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d6fdd0fa05ec21151a28c516adcb224f5e9b0ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409830"
---
# <a name="ole-background-mfc-implementation"></a>OLE-Hintergrund: MFC-Implementierung

Aufgrund der Größe und Komplexität der raw OLE-API kann das Aufrufen dieser direkt, um OLE-Anwendungen zu schreiben sehr zeitaufwändig sein. Das Ziel der Microsoft Foundation Class Library-Implementierung von OLE ist den Arbeitsaufwand zu reduzieren, was tun man, um voll funktionsfähige, OLE-fähige Anwendungen zu schreiben.

Dieser Artikel beschreibt die Teile der OLE-API, die nicht in MFC implementiert wurden. Die Diskussion wird erläutert, wie was implementiert die OLE-Abschnitt des Windows SDK zugeordnet.

##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Nicht von der Klassenbibliothek implementiert OLE-Teile

Einige Schnittstellen und der OLE-Funktionen werden von MFC nicht direkt bereitgestellt. Wenn Sie diese Funktionen verwenden möchten, können Sie die OLE-API direkt aufrufen.

IMoniker-Schnittstelle der `IMoniker` Schnittstelle wird von der Klassenbibliothek implementiert (z. B. die `COleServerItem` Klasse), aber nicht zuvor dem Programmierer verfügbar gemacht wurde. Weitere Informationen zu dieser Schnittstelle finden Sie in der OLE-Moniker-Implementierungen in der OLE-Abschnitt des Windows SDK. Siehe jedoch auch Klasse [CMonikerFile](../mfc/reference/cmonikerfile-class.md) und [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

IUnknown und IMarshal-Schnittstellen der `IUnknown` Schnittstelle wird von der Klassenbibliothek implementiert, aber nicht für den Programmierer verfügbar gemacht. Die `IMarshal` Schnittstelle ist nicht von der Klassenbibliothek implementiert, jedoch wird intern verwendet. Automatisierungsserver, der bereits mit die Klassenbibliothek erstellt haben, Marshalling von integrierten Funktionen.

Verbunddateien Docfiles (Verbunddateien) werden von der Klassenbibliothek teilweise unterstützt. Keine der Funktionen, die abgesehen von der Erstellung-compound-Dateien direkt bearbeiten werden unterstützt. MFC verwendet Klasse `COleFileStream` zur Unterstützung der Bearbeitung von Streams mit den Funktionen der standard-Datei. Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../mfc/containers-compound-files.md).

In-Process-Server und-objekthandlern-In-Process-Server und-objekthandlern können die Implementierung der visuellen Bearbeiten von Daten oder vollständige Component Object Model (COM)-Objekten in einer Dynamic Link Library (DLL). Zu diesem Zweck können Sie die DLL implementieren, durch die OLE-API direkt aufrufen. Jedoch wenn Sie einen Automatisierungsserver schreiben und der Server keine Benutzeroberfläche hat, können Sie AppWizard stellen Ihre Server in-Process-Server und vollständig in eine DLL. Weitere Informationen zu diesen Themen finden Sie unter [Automatisierungsserver](../mfc/automation-servers.md).

> [!TIP]
>  Die einfachste Möglichkeit zum Implementieren eines Automatisierungsservers ist es in einer DLL zu platzieren. MFC unterstützt diesen Ansatz.

Weitere Informationen dazu, wie die Microsoft Foundation OLE-Klassen für OLE-Schnittstellen implementieren, finden Sie unter Technische Hinweise zu MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), und [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="see-also"></a>Siehe auch

[OLE-Hintergrund](../mfc/ole-background.md)<br/>
[OLE-Hintergrund: Implementierungsstrategien](../mfc/ole-background-implementation-strategies.md)

