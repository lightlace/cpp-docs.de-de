---
title: 'OLE-Hintergrund: MFC-Implementierung | Microsoft Docs'
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
ms.openlocfilehash: d77d603c198adad2ca2c827c355ff8f6808bff66
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930325"
---
# <a name="ole-background-mfc-implementation"></a>OLE-Hintergrund: MFC-Implementierung
Aufgrund der Größe und Komplexität der unformatierten OLE-API kann das Aufrufen dieser zum Schreiben von OLE-Anwendungen direkt sehr zeitaufwändig sein. Das Ziel der Microsoft Foundation Class Library-Implementierung von OLE ist der verbleibende Arbeitsaufwand zu reduzieren, Sie müssen lediglich mit umfassenden, OLE-fähige Anwendungen schreiben können.  
  
 Dieser Artikel beschreibt die Teile der OLE-API, die nicht innerhalb von MFC implementiert wurden. Die Beschreibung wird auch erläutert, wie was implementiert, wird der OLE-Abschnitt des Windows SDK zugeordnet.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Nicht von der Klassenbibliothek implementiert OLE-Teile  
 Einige Schnittstellen und OLE-Funktionen werden von MFC nicht direkt bereitgestellt. Wenn Sie diese Funktionen nicht verwenden möchten, können Sie die OLE-API direkt aufrufen.  
  
 IMoniker-Schnittstelle  
 Die `IMoniker` Schnittstelle wird von der Klassenbibliothek implementiert (z. B. die `COleServerItem` Klasse), aber für den Programmierer vorher nicht verfügbar gemacht wurde. Weitere Informationen über diese Schnittstelle finden Sie in der OLE-Moniker-Implementierungen in der OLE-Abschnitt des Windows SDK. Siehe jedoch auch Klasse [CMonikerFile](../mfc/reference/cmonikerfile-class.md) und [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 IUnknown und IMarshal-Schnittstellen  
 Die `IUnknown` Schnittstelle wird von der Klassenbibliothek implementiert, aber nicht für den Programmierer verfügbar gemacht. Die `IMarshal` Schnittstelle ist nicht von der Klassenbibliothek implementiert, jedoch wird intern verwendet. Automatisierungsserver, die bereits mit die Klassenbibliothek erstellt haben, Marshalling-Funktionen.  
  
 Docfiles (Verbunddateien)  
 Verbunddateien werden von der Klassenbibliothek teilweise unterstützt. Keine der Funktionen, die direkt Verbunddateien abgesehen von der Erstellung bearbeiten werden unterstützt. MFC verwendet Klasse `COleFileStream` Manipulation von Datenströmen mit standard-Datei-Funktionen zu unterstützen. Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../mfc/containers-compound-files.md).  
  
 In-Process-Servern und Objekthandler  
 In-Process-Servern und Objekthandler können die Implementierung von visual Bearbeiten von Daten oder vollständige Component Object Model (COM)-Objekten in einer Dynamic Link Library (DLL). Zu diesem Zweck können Sie die DLL implementieren, durch die OLE-API direkt aufrufen. Wenn Sie eines Automatisierungsservers schreiben, und der Server keine Benutzeroberfläche hat, Sie können jedoch AppWizard stellen Ihre Server in-Process-Server, und fügen Sie sie vollständig in eine DLL. Weitere Informationen zu diesen Themen finden Sie unter [Automatisierungsserver](../mfc/automation-servers.md).  
  
> [!TIP]
>  Die einfachste Möglichkeit zum Implementieren eines Automatisierungsservers ist es in einer DLL zu platzieren. MFC unterstützt diesen Ansatz.  
  
 Weitere Informationen wie die Microsoft Foundation-OLE-Klassen OLE-Schnittstellen implementieren, finden Sie technische Hinweise zu MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), und [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
## <a name="see-also"></a>Siehe auch  
 [OLE-Hintergrund](../mfc/ole-background.md)   
 [OLE-Hintergrund: Implementierungsstrategien](../mfc/ole-background-implementation-strategies.md)

