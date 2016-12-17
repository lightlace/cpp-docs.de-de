---
title: "OLE-Hintergrund: MFC-Implementierung"
ms.custom: na
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IMarshall"
  - "IMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMarshall-Klasse"
  - "IMoniker-Schnittstelle, MFC"
  - "MFC-Bibliotheken, Implementieren"
  - "OLE IMarshal-Schnittstelle"
  - "OLE-IMoniker-Schnittstelle"
  - "OLE-IUnknown"
  - "OLE-MFC-Bibliothekimplementierung"
  - "OLE, Verbunddateien"
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# OLE-Hintergrund: MFC-Implementierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aufgrund die Größe und Komplexität unformatierter OLE\-API, diese direkt aufrufen kann, um OLE\-Anwendungen schreiben sehr zeitaufwendig sein.  Das Ziel der Microsoft Foundation Class\-Bibliotheks\-Implementierung von OLE ist, dadurch den erforderlichen Arbeitsaufwand reduzieren, den Sie ausführen müssen, um die Vollfunktions\-, OLE\-fähigen Anwendungen zu schreiben.  
  
 In diesem Artikel werden die Teile der OLE\-API, die in MFC nicht implementiertes wurden.  Die Erläuterung wird auch beschrieben, z was implementierte Zuordnungen zum OLE\-Abschnitt [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] ist.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Teile OLE implementiert nicht von der Klassenbibliothek  
 Einige Schnittstellen und Funktionen von OLE werden nicht direkt von MFC bereitgestellt.  Wenn Sie diese Features verwenden möchten, können Sie die OLE\-API direkt aufrufen.  
  
 IMoniker\-Schnittstelle  
 Die `IMoniker`\-Schnittstelle wird von der Klassenbibliothek implementiert \(beispielsweise die Klasse `COleServerItem` \), aber nicht zuvor den Programmierer verfügbar gemacht wurde.  Weitere Informationen über diese Schnittstelle, finden Sie OLE\-Moniker\-Implementierungen im OLE\-Abschnitt [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Allerdings wird auch die Klassen [CMonikerFile](../mfc/reference/cmonikerfile-class.md) und [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 IUnknown und IMarshal\-Schnittstellen  
 Die **IUnknown**\-Schnittstelle wird implementiert, von der Klassenbibliothek wird jedoch nicht für den Programmierer verfügbar gemacht.  Die **IMarshal**\-Schnittstelle wird nicht implementiert, von der Klassenbibliothek wird aber intern verwendet.  Die Automatisierungsserver, die mithilfe der Klassenbibliothek besitzen erstellt werden bereits, die integrierten Marshallingfunktionen.  
  
 Docfiles \(Verbunddateien\)  
 Verbunddateien werden teilweise von der Klassenbibliothek unterstützt.  Keine der Funktionen, die direkt Verbunddateien zum Erstellen hinaus bearbeiten, werden unterstützt.  MFC\-Verwendung Klassen **COleFileStream**, um die Bearbeitung von Streams mit Standarddateifunktionen zu unterstützen.  Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../mfc/containers-compound-files.md).  
  
 Prozessinterne Server und Objekthandler  
 Prozessinterne Server und Objekthandler ermöglichen Implementierung von visuellen Bearbeiten von Daten oder von vollständigen Component Object Model \(COM\)\- Objekten in einer Dynamic Link Library \(DLL\).  Um dies zu erreichen, können Sie Ihre DLL implementieren indem Sie direkt die OLE\-API aufrufen.  Wenn Sie einen Automatisierungsserver programmieren und der Server keine Benutzeroberfläche aufweist, können Sie Anwendungen verwenden, um den Server als prozessinternen Server zu erstellen und ihn vollständig in eine DLL eingefügt.  Weitere Informationen zu diesen Themen, finden Sie unter [Automatisierungsserver](../mfc/automation-servers.md).  
  
> [!TIP]
>  Die einfachste Möglichkeit, einen Automatisierungsserver zu implementieren ist, in einer DLL zu platzieren.  MFC unterstützt diesen Ansatz.  
  
 Weitere Informationen darüber, wie die die Klassen der Microsoft Foundation OLE OLE\-Schnittstellen implementieren, finden Sie Technische Hinweise zu MFC unter [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md) und [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
## Siehe auch  
 [OLE\-Hintergrund](../mfc/ole-background.md)   
 [OLE\-Hintergrund: Implementierungsstrategien](../mfc/ole-background-implementation-strategies.md)