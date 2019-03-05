---
title: Verwalten von Daten mit Dokumentdatenvariablen
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
ms.openlocfilehash: dc21bd4b3dbe7609a33af4b4f93f15a3f5c9a64e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259970"
---
# <a name="managing-data-with-document-data-variables"></a>Verwalten von Daten mit Dokumentdatenvariablen

Implementieren Sie die Daten des Dokuments als Membervariablen der Dokumentklasse. Das Scribble-Programm deklariert beispielsweise einen Datenmember vom Typ `CObList` – eine verknüpfte Liste, die Zeiger auf speichert `CObject` Objekte. Diese Liste wird verwendet, um Arrays von Punkten zu speichern, die eine Zeile das Freihandzeichnen bilden.

Wie Sie die Daten des Dokuments Member implementieren, hängt von der Art der Anwendung ab. Damit können Sie sich, MFC-stellt eine Gruppe von "Collection Classes" bereit, Arrays, Listen und Zuordnungen (Wörterbücher), einschließlich Sammlungen, die basierend auf C++-Vorlagen – zusammen mit Klassen, die eine Vielzahl von allgemeine Datentypen wie z. B. kapseln `CString`, `CRect`, `CPoint`, `CSize`, und `CTime`. Weitere Informationen zu diesen Klassen finden Sie unter den [Übersicht über die Klassenbibliothek](../mfc/class-library-overview.md) in die *MFC-Referenz*.

Wenn Sie die Daten des Dokuments Member definieren, fügen in der Regel Sie Memberfunktionen der Dokument-Klasse zum Festlegen und Abrufen von Daten und andere nützliche Vorgänge auf diesen ausführen.

Ihre Ansichten zugreifen, dass das Document-Objekt mit der Ansicht Zeiger auf das Dokument, in der Ansicht zum Zeitpunkt der Erstellung installiert. Sie können die this-Zeiger in Member-Funktionen für eine Sicht abrufen, durch den Aufruf der `CView` Memberfunktion `GetDocument`. Achten Sie darauf, dass Sie diesen Zeiger auf den Dokumenttyp umgewandelt. Anschließend können Sie Mitglieder der öffentlichen Dokument über den Zeiger zugreifen.

Wenn häufig die Datenübertragung direkten Zugriff einen oder die nicht öffentliche Member der Document-Klasse verwenden möchten, empfiehlt es sich um die Ansicht, die einen "Friend" (in C++-Bedingungen) der Document-Klasse zu Klasse machen.

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)
