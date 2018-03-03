---
title: "Auswählen eines Grafikobjekts einen Gerätekontext | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5909625b816deb1303821aaec4034fa24f29be5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Auswählen eines Grafikobjekts für einen Gerätekontext
Dieses Thema gilt für die Verwendung von Grafikobjekten in einem Fenster Gerätekontext. Nachdem Sie [erstellen Sie ein Objekt](../mfc/one-stage-and-two-stage-construction-of-objects.md), müssen Sie es in den Gerätekontext anstelle der Default-Objekt, die dort gespeicherten auswählen:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## <a name="lifetime-of-graphic-objects"></a>Lebensdauer von Grafikobjekten  
 Die zurückgegebene Grafikobjekt [SelectObject](../mfc/reference/cdc-class.md#selectobject) ist "temporär". Es wird also gelöscht werden, von der [OnIdle](../mfc/reference/cwinapp-class.md#onidle) Memberfunktion der Klasse `CWinApp` Uhrzeit der nächsten Ausführung des Programms im Leerlauf ruft. Solange Sie das zurückgegebene Objekt verwenden `SelectObject` in einer einzelnen Funktion ohne Zurückgeben der Steuerung an die Haupt-Nachrichtenschleife müssen kein Problem.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Grafikobjekte](../mfc/graphic-objects.md)  
  
-   [Ein- und zweistufige Konstruktion von Grafikobjekten](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Grafikobjekte](../mfc/graphic-objects.md)

