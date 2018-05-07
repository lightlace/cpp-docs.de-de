---
title: 'Ausnahmen: OLE-Ausnahmen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 991848e9b5b78ad960fb8ed0bdf09dd56db47e2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-ole-exceptions"></a>Ausnahmen: OLE-Ausnahmen
Die Techniken und Funktionen zum Behandeln von Ausnahmen in OLE entsprechen denen für andere Ausnahmebehandlung. Weitere Informationen zur Ausnahmebehandlung finden Sie im Artikel [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
 Alle Ausnahmeobjekte sind von der abstrakten Basisklasse abgeleitete `CException`. MFC stellt zwei Klassen für die Behandlung von OLE-Ausnahmen:  
  
-   [COleException](../mfc/reference/coleexception-class.md) für die Behandlung allgemeiner OLE-Ausnahmen.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) für generieren und Behandeln von OLE-Ausnahmen (Automatisierung Dispatch).  
  
 Der Unterschied zwischen diesen beiden Klassen ist die Menge an Informationen, die sie bieten und wo sie verwendet werden. `COleException` verfügt über einen öffentlichen Datenmember, der den OLE-Statuscode für die Ausnahme enthält. `COleDispatchException` Liefert Informationen, u. a. folgende:  
  
-   Einen anwendungsspezifischen Fehlercode  
  
-   Eine Beschreibung, wie z. B. "Datenträger ist voll"  
  
-   Ein Hilfekontext, den Ihre Anwendung, zum Bereitstellen zusätzlicher Informationen für den Benutzer verwenden können  
  
-   Der Name der Hilfedatei für Ihre Anwendung  
  
-   Der Name der Anwendung, die die Ausnahme generiert hat  
  
 `COleDispatchException` Stellt Informationen bereit, sodass mit Produkten wie Microsoft Visual Basic verwendet werden kann. Die verbale fehlerbeschreibung kann in einem Meldungsfeld oder einer sonstigen Benachrichtigung verwendet werden. die Hilfe-Informationen kann verwendet werden, können die Benutzer auf die Bedingungen zu reagieren, die die Ausnahme verursacht hat.  
  
 Zwei globale Funktionen entsprechen den zwei OLE-Ausnahmeklassen: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) und [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Verwenden Sie diese bzw. allgemeiner OLE-Ausnahmen und OLE-Dispatch-Ausnahmen auslöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

