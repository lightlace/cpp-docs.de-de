---
title: Initialisieren von Dokumenten und Ansichten | Microsoft-Dokumentation
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
ms.openlocfilehash: d6a6f989b8c6b19c78cf9ad508d18e9592bb9305
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417396"
---
# <a name="initializing-documents-and-views"></a>Initialisieren von Dokumenten und Ansichten

Dokumente werden auf zwei unterschiedliche Arten erstellt werden, damit die Dokumentklasse in beide Richtungen unterstützen muss. Erstens kann der Benutzer ein neues, leeres Dokument mit dem Befehl neue Datei erstellen. Initialisieren Sie das Dokument in der Überschreibung der in diesem Fall die [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) Memberfunktion der Klasse [CDocument](../mfc/reference/cdocument-class.md). Zweitens kann der Benutzer verwenden den Befehl zum Öffnen im Menü Datei auf ein neues Dokument erstellen, deren Inhalt aus einer Datei gelesen werden. Initialisieren Sie das Dokument in der Überschreibung der in diesem Fall die [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) Memberfunktion der Klasse `CDocument`. Wenn beide Initialisierungen identisch sind, können Sie eine allgemeine Memberfunktion aufrufen, aus beiden Außerkraftsetzungen oder `OnOpenDocument` Aufrufen `OnNewDocument` initialisieren ein sauberes Dokument, und schließen Sie dann den öffnen-Vorgang.

Sichten werden erstellt, nachdem ihre Dokumente erstellt werden. Der beste Zeitpunkt zum Initialisieren Sie eine Ansicht ist nach das Framework erstellen, das Dokument, Rahmenfenster und anzeigen. Sie können die Ansicht initialisieren, durch Überschreiben der [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Memberfunktion [CView](../mfc/reference/cview-class.md). Wenn Sie erneut initialisieren, oder passen Sie alles benötigen jedes Mal, wenn das Dokument ändert, können Sie überschreiben [OnUpdate](../mfc/reference/cview-class.md#onupdate).

## <a name="see-also"></a>Siehe auch

[Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

