---
title: Dokumentvorlagenklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: 2589bc8f04e791f73529af91ffb148c2c717cd08
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294576"
---
# <a name="document-template-classes"></a>Dokumentvorlagenklassen

Dokumentvorlage Objekte Koordination der Erstellung des Dokuments, Ansicht und Frame-Windows-Objekte, wenn ein neues Dokument oder Sicht erstellt wird.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
Die Basisklasse für Dokumentvorlagen. Diese Klasse wird nie direkt verwendet werden; Stattdessen verwenden Sie eine der anderen Dokumentvorlage Klassen von dieser Klasse abgeleitet.

[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)<br/>
Eine Vorlage für Dokumente in die multiple Document Interface (MDI). MDI-Anwendungen können mehrere Dokumente gleichzeitig geöffnet haben.

[CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)<br/>
Eine Vorlage für Dokumente in die single Document Interface (SDI). SDI-Anwendungen müssen nur ein Dokument gleichzeitig öffnen.

## <a name="related-class"></a>Verwandte Klasse

[CCreateContext](../mfc/reference/ccreatecontext-structure.md)<br/>
Eine Struktur, die von einer Dokumentvorlage an fenstererstellung Funktionen, um das Erstellen von Dokument, Ansicht und dem Rahmenfenster Objekten zu koordinieren übergeben werden.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
