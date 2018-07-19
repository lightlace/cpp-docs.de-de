---
title: 'Zwischenablage: Hinzufügen anderer Formate | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67004ac43193d47720626da241a8030ba396abdf
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932017"
---
# <a name="clipboard-adding-other-formats"></a>Zwischenablage: Hinzufügen anderer Formate
In diesem Thema wird erläutert, wie Sie die Liste der unterstützten Formate, insbesondere für OLE-Unterstützung zu erweitern. Das Thema [Zwischenablage: Daten kopieren und Einfügen](../mfc/clipboard-copying-and-pasting-data.md) beschreibt die minimale Implementierung, die erforderlich ist, kopieren und Einfügen aus der Zwischenablage zu unterstützen. Ist dies alle Sie implementieren, sind die einzigen Formate, die in der Zwischenablage platziert **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**, und möglicherweise **CF_LINKSOURCE**. Die meisten Anwendungen benötigen mehr Formate in der Zwischenablage als dieser drei.  
  
##  <a name="_core_registering_custom_formats"></a> Registrieren benutzerdefinierter Datenformate  
 Um eine eigene benutzerdefinierte Formate zu erstellen, halten Sie die gleiche Prozedur, die Sie verwenden, wenn alle benutzerdefiniertes Format der Zwischenablage zu registrieren: übergeben Sie den Namen des Formats, das die **RegisterClipboardFormat** Funktion, und verwenden Sie den Rückgabewert als Format-ID.  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> Platzieren von Formaten in die Zwischenablage  
 Um weitere Formate, die in der Zwischenablage platziert hinzuzufügen, müssen Sie überschreiben die `OnGetClipboardData` Funktion in der Sie von einer abgeleiteten Klasse `COleClientItem` oder `COleServerItem` (je nachdem, ob die Daten kopiert werden systemeigene). In dieser Funktion sollten Sie das folgende Verfahren verwenden.  
  
#### <a name="to-place-formats-on-the-clipboard"></a>Platzieren von Formaten in die Zwischenablage  
  
1.  Erstellen eines `COleDataSource`-Objekts  
  
2.  Übergeben Sie diese Datenquelle an eine Funktion, die die Liste der unterstützten Formate durch Aufrufen der systemeigene Datenformate hinzufügt `COleDataSource::CacheGlobalData`.  
  
3.  Hinzufügen von Standardformaten durch Aufrufen von `COleDataSource::CacheGlobalData` für jedes Standardformat, die Sie unterstützen möchten.  
  
 Diese Technik wird verwendet, in der MFC-OLE-Beispielprogramm [HIERSVR](../visual-cpp-samples.md) (Überprüfen Sie die `OnGetClipboardData` Memberfunktion von der **CServerItem** Klasse). Der einzige Unterschied in diesem Beispiel ist dieser Schritt 3 nicht implementiert ist, da HIERSVR keine weiteren Standardformate unterstützt.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [OLE-Objekte und Daten Datenquellen und uniform Data transfer](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE- Drag & drop](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

