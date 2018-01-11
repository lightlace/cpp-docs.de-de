---
title: Asynchrone Moniker im Internet | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd7b6be66c3049c1d82aa549cf362a840fd6f265
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asynchronous-monikers-on-the-internet"></a>Asynchrone Moniker im Internet
Im Internet werden neue Ansätze zum Anwendungsentwurf aufgrund Zugriffsvorgang langsames Netzwerk erfordert. Anwendungen sollten Netzwerkzugriff asynchron, um zu vermeiden, führte die Benutzeroberfläche ausführen. Die MFC-Klasse [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) stellt asynchrone Unterstützung zum Herunterladen von Dateien.  
  
 Sie können mit asynchronen Monikern die COM-Anwendung, um asynchron über das Internet herunterladen und progressiven Darstellung von großen Objekten wie z. B. Bitmaps und VRML-Objekte bereitzustellen erweitern. Asynchrone Moniker ermöglichen eine ActiveX-Steuerelementeigenschaft oder eine Datei im Internet heruntergeladen werden, ohne Blockierung die Antwort der Benutzeroberfläche.  
  
## <a name="advantages-of-asynchronous-monikers"></a>Vorteile von asynchronen Monikern  
 Sie können asynchrone Moniker verwenden:  
  
-   Herunterladen von Code und Dateien ohne zu blockieren.  
  
-   Downloadeigenschaften Sie in ActiveX-Steuerelemente ohne zu blockieren.  
  
-   Empfang von Benachrichtigungen über Downloadfortschritt.  
  
-   Nachverfolgen des Status "und" Status "bereit" Informationen ".  
  
-   Liefert Statusinformationen für den Benutzer zur Bearbeitung an.  
  
-   Ermöglicht dem Benutzer das Herunterladen jederzeit abbrechen.  
  
## <a name="mfc-classes-for-asynchronous-monikers"></a>MFC-Klassen für asynchronen Monikern  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) stammt aus [CMonikerFile](../mfc/reference/cmonikerfile-class.md), die wiederum von abgeleitet ist [COleStreamFile](../mfc/reference/colestreamfile-class.md). Ein `COleStreamFile` Objekt stellt einen Datenstrom von Daten; einen `CMonikerFile` object verwendet ein `IMoniker` zum Abrufen der Daten und ein `CAsyncMonikerFile` Objekt tut asynchron.  
  
 Asynchrone Moniker dienen in erster Linie im Internet-fähigen Anwendungen und ActiveX-Steuerelemente eine reagierende Benutzeroberfläche während der Übertragung von Dateien anzugeben. Ein gutes Beispiel hierfür ist die Verwendung von [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) ActiveX-Steuerelemente asynchrone Eigenschaften bereit.  
  
## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>MFC-Klassen für Datenpfade in ActiveX-Steuerelementen  
 Die MFC-Klassen `CDataPathProperty` und [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) Implementieren von ActiveX-Steuerelement-Eigenschaften, die asynchron geladen werden können. Asynchrone Eigenschaften werden nach der synchronen Initiierung geladen. Asynchrone ActiveX-Steuerelemente rufen wiederholt einen Rückruf, um die Verfügbarkeit der neuen Daten während einer langwierigen Eigenschaft Exchange anzugeben.  
  
 `CDataPathProperty` wird von `CAsyncMonikerFile` abgeleitet. `CCachedDataPathProperty` wird von `CDataPathProperty` abgeleitet. Um asynchrone Eigenschaften in der ActiveX-Steuerelementen zu implementieren, leiten Sie eine Klasse von `CDataPathProperty` oder `CCachedDataPathProperty`, und überschreiben [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) und andere Benachrichtigungen Sie erhalten möchten.  
  
#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Zum Herunterladen einer Datei, die Verwendung von asynchronen Monikern  
  
1.  Deklarieren Sie eine Klasse abgeleitet [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
2.  Überschreiben Sie [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) zum Anzeigen der Daten.  
  
3.  Überschreiben Sie die anderen Memberfunktionen, einschließlich [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), und [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding).  
  
4.  Deklarieren Sie eine Instanz dieser Klasse und verwenden sie zum Öffnen von URLs.  
  
 Informationen zum Herunterladen von asynchron in einem ActiveX-Steuerelement finden Sie unter [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

