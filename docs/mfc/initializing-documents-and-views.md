---
title: Initialisieren von Dokumenten und Ansichten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f80d870f9804454dc652fdda00f34fcdb7a52062
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-documents-and-views"></a>Initialisieren von Dokumenten und Ansichten
Dokumente werden auf zwei unterschiedliche Arten erstellt werden, damit Ihre Dokumentklasse beide Methoden unterstützen. Erstens kann der Benutzer ein neues, leeres Dokument mit dem Befehl neue Datei erstellen. In diesem Fall initialisiert das Dokument in der Ihre Überschreibung der [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) Memberfunktion der Klasse [CDocument](../mfc/reference/cdocument-class.md). Zweitens kann der Benutzer verwenden den Befehl Öffnen im Menü Datei auf ein neues Dokument erstellen, deren Inhalt aus einer Datei gelesen werden. In diesem Fall initialisiert das Dokument in der Ihre Überschreibung der [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) Memberfunktion der Klasse **CDocument**. Wenn beide Initialisierungen identisch sind, können Sie eine allgemeine Memberfunktion aufrufen, aus der beiden Außerkraftsetzungen oder `OnOpenDocument` erreichen `OnNewDocument` so initialisieren ein sauberes Dokument und anschließend den öffnen-Vorgang abzuschließen.  
  
 Sichten werden erstellt, nachdem ihre Dokumente erstellt werden. Der beste Zeitpunkt zum Initialisieren einer Ansicht ist, nachdem das Framework abgeschlossen ist, erstellen das Dokument, die Rahmenfenster und die Ansicht. Sie können die Ansicht initialisieren, durch Überschreiben der [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Memberfunktion von [CView](../mfc/reference/cview-class.md). Wenn Sie erneut zu initialisieren, oder passen Sie alle Elemente müssen jedes Mal, wenn das Dokument geändert wird, können Sie überschreiben [OnUpdate](../mfc/reference/cview-class.md#onupdate).  
  
## <a name="see-also"></a>Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

