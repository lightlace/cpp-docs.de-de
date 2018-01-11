---
title: Drag & Drop (OLE) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a852e597c06a08c3e9eb83731dc7da7df077435
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-ole"></a>Drag & Drop (OLE)
Die Drag-and-Drop-Funktion von OLE ist in erster Linie eine Verknüpfung zum Kopieren und Einfügen von Daten. Wenn Sie die Zwischenablage kopieren oder Einfügen von Daten verwenden, sind eine Reihe von Schritten erforderlich. Wählen Sie die Daten, klicken Sie auf **Ausschneiden** oder **Kopie** aus der **bearbeiten** Menü, wechseln Sie zu der Zieldatei, die im Fenster oder die Anwendung, platzieren Sie den Cursor in den gewünschten Speicherort ein, und klicken Sie auf **Einfügen** aus der **bearbeiten** Menü.  
  
 OLE- Drag & Drop unterscheidet sich von den Manager für Dateiserver Drag-and-Drop-Mechanismus, der Dateinamen nur behandeln und wurde speziell für Dateinamen an Anwendungen übergeben. OLE-Drag und Drop ist weitaus Allgemein. Sie können Drag & drop-alle Daten, die auch in der Zwischenablage platziert werden konnte.  
  
 Bei Verwendung von OLE- Drag & Drop entfernen Sie zwei Schritte des Prozesses an. Sie wählen Sie die Daten aus dem Quellcodefenster angezeigt (die "Ablagequelle"), ziehen Sie es an das gewünschte Ziel ("Drop Target") und löschen Sie es, indem Sie die Maustaste loslassen. Der Vorgang entfällt die Notwendigkeit für Menüs und ist schneller, als die Sequenz kopieren/einfügen. Die einzige Voraussetzung ist, dass die Drop-Quelle und die Drop-Ziel öffnen und zumindest teilweise auf dem Bildschirm sichtbar sein müssen.  
  
 Verwenden OLE- Drag & Drop, können Daten von einem Speicherort zu einem anderen in einem Dokument, zwischen verschiedenen Dokumenten oder Anwendungen übertragen werden. In einem Container oder einer Server-Anwendung implementiert werden kann, und jede Anwendung kann eine Drop-Quelle, Drop-Ziel oder beides sein. Wenn eine Anwendung Drop-Quelle und Drop-Ziel unterstützt, ist Drag & Drop aktiviert zwischen untergeordneten Fenstern oder innerhalb eines Fensters. Diese Funktion kann die Anwendung wesentlich leichter machen.  
  
 Wenn Sie nur die Drag-and-Drop-Funktionen von OLE verwenden möchten, finden Sie unter [Drag & Drop: Anpassen von](../mfc/drag-and-drop-customizing.md). Die Verfahren in diesem Artikel erläutert können Sie nicht-OLE-Anwendungen, die Quellen löschen machen. Der Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../mfc/drag-and-drop-implementing-a-drop-target.md) beschreibt das Ablageziel Unterstützung für OLE und nicht-OLE-Anwendungen zu implementieren. Es ist auch hilfreich sein, überprüfen Sie die MFC-OLE-Beispiele [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md).  
  
 Wenn Sie nicht gelesen haben die [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md) Artikelreihe, Sie sollten, dies jetzt nachzuholen. Dieser Artikel erläutert die Grundlagen der Datenübertragung und wie Sie es in Ihren Anwendungen implementieren.  
  
 Weitere Informationen über Drag & Drop finden Sie unter:  
  
-   [Drag &Drop: Implementieren einer Drag & Drop-Quelle](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Drag & Drop: Implementieren eines Drag & Drop-Ziels](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Drag & Drop: Anpassen](../mfc/drag-and-drop-customizing.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md)

