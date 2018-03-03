---
title: 'Ausnahmen: OLE-Ausnahmen | Microsoft Docs'
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
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67be1947b3fa08c26d659838922ce42a905167a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-ole-exceptions"></a>Ausnahmen: OLE-Ausnahmen
Die Techniken und Funktionen zum Behandeln von Ausnahmen in OLE entsprechen denen für andere Ausnahmebehandlung. Weitere Informationen zur Ausnahmebehandlung finden Sie im Artikel [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
 Alle Ausnahmeobjekte sind von der abstrakten Basisklasse abgeleitete `CException`. MFC stellt zwei Klassen für die Behandlung von OLE-Ausnahmen:  
  
-   [COleException](../mfc/reference/coleexception-class.md) für die Behandlung allgemeiner OLE-Ausnahmen.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) für generieren und Behandeln von OLE-Ausnahmen (Automatisierung Dispatch).  
  
 Der Unterschied zwischen diesen beiden Klassen ist die Menge an Informationen, die sie bieten und wo sie verwendet werden. `COleException`verfügt über einen öffentlichen Datenmember, der den OLE-Statuscode für die Ausnahme enthält. `COleDispatchException`Liefert Informationen, u. a. folgende:  
  
-   Einen anwendungsspezifischen Fehlercode  
  
-   Eine Beschreibung, wie z. B. "Datenträger ist voll"  
  
-   Ein Hilfekontext, den Ihre Anwendung, zum Bereitstellen zusätzlicher Informationen für den Benutzer verwenden können  
  
-   Der Name der Hilfedatei für Ihre Anwendung  
  
-   Der Name der Anwendung, die die Ausnahme generiert hat  
  
 `COleDispatchException`Stellt Informationen bereit, sodass mit Produkten wie Microsoft Visual Basic verwendet werden kann. Die verbale fehlerbeschreibung kann in einem Meldungsfeld oder einer sonstigen Benachrichtigung verwendet werden. die Hilfe-Informationen kann verwendet werden, können die Benutzer auf die Bedingungen zu reagieren, die die Ausnahme verursacht hat.  
  
 Zwei globale Funktionen entsprechen den zwei OLE-Ausnahmeklassen: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) und [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Verwenden Sie diese bzw. allgemeiner OLE-Ausnahmen und OLE-Dispatch-Ausnahmen auslöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

