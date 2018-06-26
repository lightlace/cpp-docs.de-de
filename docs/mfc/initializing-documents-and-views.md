---
title: Initialisieren von Dokumenten und Ansichten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43610a08d5a3713cc40de0a2279286735a27d1da
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928181"
---
# <a name="initializing-documents-and-views"></a>Initialisieren von Dokumenten und Ansichten
Dokumente werden auf zwei unterschiedliche Arten erstellt werden, damit Ihre Dokumentklasse beide Methoden unterstützen. Erstens kann der Benutzer ein neues, leeres Dokument mit dem Befehl neue Datei erstellen. In diesem Fall initialisiert das Dokument in der Ihre Überschreibung der [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) Memberfunktion der Klasse [CDocument](../mfc/reference/cdocument-class.md). Zweitens kann der Benutzer verwenden den Befehl Öffnen im Menü Datei auf ein neues Dokument erstellen, deren Inhalt aus einer Datei gelesen werden. In diesem Fall initialisiert das Dokument in der Ihre Überschreibung der [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) Memberfunktion der Klasse `CDocument`. Wenn beide Initialisierungen identisch sind, können Sie eine allgemeine Memberfunktion aufrufen, aus der beiden Außerkraftsetzungen oder `OnOpenDocument` erreichen `OnNewDocument` so initialisieren ein sauberes Dokument und anschließend den öffnen-Vorgang abzuschließen.  
  
 Sichten werden erstellt, nachdem ihre Dokumente erstellt werden. Der beste Zeitpunkt zum Initialisieren einer Ansicht ist, nachdem das Framework abgeschlossen ist, erstellen das Dokument, die Rahmenfenster und die Ansicht. Sie können die Ansicht initialisieren, durch Überschreiben der [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Memberfunktion von [CView](../mfc/reference/cview-class.md). Wenn Sie erneut zu initialisieren, oder passen Sie alle Elemente müssen jedes Mal, wenn das Dokument geändert wird, können Sie überschreiben [OnUpdate](../mfc/reference/cview-class.md#onupdate).  
  
## <a name="see-also"></a>Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

