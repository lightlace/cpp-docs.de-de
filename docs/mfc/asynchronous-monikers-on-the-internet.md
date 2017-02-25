---
title: "Asynchrone Moniker im Internet | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Asynchron"
  - "Asynchroner Moniker [C++]"
  - "Herunterladen von Internetressourcen und asynchronen Monikern"
  - "Internet [C++], Asynchrones Herunterladen"
  - "MFC [C++], Asynchroner Moniker"
  - "Optimierung [C++], Asynchrones Herunterladen über das Internet"
  - "Webanwendungen [C++], Asynchron"
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Asynchrone Moniker im Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Internet erfordert neue Konzepte den Anwendungsentwurf aufgrund des langsamen Netzwerkzugriff simuliert.  Anwendungen sollten Netzwerkzugriff asynchron ausführen, um die Benutzeroberfläche, festzuklemmen zu vermeiden.  Die abgeleitete MFC\-Klasse [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) bietet Unterstützung für das asynchrone Herunterladen von Dateien.  
  
 Mit asynchronen Monikern können Sie der COM\-Anwendung erweitern, über dem Internet asynchron herunterladen und progressives Rendering großer Objekte z Bitmaps und VRML\-Objekten bereitzustellen.  Asynchrone Moniker aktivieren eine ActiveX\-Steuerelement\-Eigenschaft oder eine Datei auf dem ohne die Antwort der Benutzeroberfläche zu blockieren heruntergeladen werden, Internet.  
  
## Vorteile von asynchronen Monikern  
 Sie können asynchrone Moniker verwenden:  
  
-   Downloadcode und \- dateien, ohne zu blockieren.  
  
-   Downloadeigenschaften in ActiveX\-Steuerelemente, ohne zu blockieren.  
  
-   Um Benachrichtigungen des Downloadingstatus.  
  
-   Nachverfolgen von Statusanzeigen und threadbereite Zustandsinformationen.  
  
-   Stellen Sie dem Benutzer Statusinformationen zum Status bereit.  
  
-   Ermöglicht dem Benutzer, die einen Download jederzeit abbrechen.  
  
## MFC\-Klassen für asynchrone Moniker  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) ist von [CMonikerFile](../mfc/reference/cmonikerfile-class.md) abgeleitet, das wiederum von [COleStreamFile](../mfc/reference/colestreamfile-class.md) abgeleitet wird.  Ein `COleStreamFile`\-Objekt stellt einen Stream von Daten dar; ein `CMonikerFile`\-Objekt verwendet `IMoniker`, um die Daten abzurufen, und ein `CAsyncMonikerFile`\-Objekt dies jetzt asynchron.  
  
 Asynchrone Moniker werden hauptsächlich in den internetaktivierten Anwendungen und in ActiveX\-Steuerelemente, eine Benutzeroberfläche mit reaktionsschnellen während der Dateiübertragungen bereitzustellen verwendet.  Ein Paradebeispiel hierfür ist die Verwendung von [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md), asynchrone Eigenschaften von ActiveX\-Steuerelementen bereitzustellen.  
  
## MFC\-Klassen für Datenpfade in ActiveX\-Steuerelemente  
 Die MFC\-Klassen `CDataPathProperty` und [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) implementieren ActiveX\-Steuerelementeigenschaften, die asynchron geladen werden können.  Asynchrone Eigenschaften werden nach synchroner Initiierung geladen.  Asynchrone ActiveX\-Steuerelemente rufen wiederholt einen Rückruf auf, um Verfügbarkeit von neuen Daten während eines längeren Eigenschaftenaustauschprozesses anzugeben.  
  
 `CDataPathProperty` ist von `CAsyncMonikerFile` abgeleitet.  `CCachedDataPathProperty` ist von `CDataPathProperty` abgeleitet.  So asynchrone Eigenschaften in den ActiveX\-Steuerelementen implementieren, eine Klasse von `CDataPathProperty` oder `CCachedDataPathProperty` abgeleitet werden, und [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) und andere Benachrichtigungen überschreiben, die Sie erhalten möchten.  
  
#### So fügen Sie eine Datei mithilfe asynchroner Moniker herunterladen  
  
1.  Deklarieren Sie eine Klasse wird von [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) abgeleitet.  
  
2.  Überschreibung [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md), um die Daten anzuzeigen.  
  
3.  Überschreiben Sie Memberfunktionen andere, einschließlich [OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md), [OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md) und [OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md).  
  
4.  Deklarieren Sie eine Instanz dieser Klasse und verwenden Sie sie, um URLs zu öffnen.  
  
 Weitere Informationen über in einem ActiveX\-Steuerelement asynchron herunterladen, finden Sie unter [ActiveX\-Steuerelemente im Internet](../mfc/activex-controls-on-the-internet.md).  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)