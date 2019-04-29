---
title: Kopf- und Fußzeilen
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
ms.openlocfilehash: 1e2e57331ccbc7f0afd7b82dc035410af495abd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297228"
---
# <a name="headers-and-footers"></a>Kopf- und Fußzeilen

In diesem Artikel erläutert das Hinzufügen von Kopf- und Fußzeilen zu einem gedruckten Dokument.

Wenn Sie sich ein Dokument auf dem Bildschirm ansehen, wird der Name des Dokuments und Ihre Position im Dokument im Allgemeinen in eine Titelleiste und eine Statusleiste angezeigt. Bei Betrachtung gedruckter eines Dokuments ist es sinnvoll, den Namen und die Seitenzahl in einer Kopf- oder Fußzeile angezeigt. Dies ist eine gängige Methode, die in der, die WYSIWYG sogar Programme unterscheiden sich in der Bildschirm- und Drucken Leistung.

Die [OnPrint](../mfc/reference/cview-class.md#onprint) Memberfunktion ist der Platz zu Kopf- oder Fußzeilen gedruckt werden, da sie für jede Seite aufgerufen wird, und da sie nur für den Druck, nicht für die Bildschirmanzeige aufgerufen wird. Sie können definieren, eine separate Funktion, um eine Kopf- oder Fußzeile zu drucken und übergeben sie den Drucker-Gerätekontext aus `OnPrint`. Sie müssen möglicherweise Fenster Ursprungs oder der Block vor dem Aufruf anpassen [OnDraw](../mfc/reference/cview-class.md#ondraw) um zu vermeiden, dass den Text der Seite Überlappung der Kopf- oder Fußzeile. Sie möglicherweise auch ändern `OnDraw` , da die Menge des Dokuments, das passt, auf der Seite reduziert werden könnten.

Eine Möglichkeit, um dies zu kompensieren, für der Bereich, die von der Kopf- oder Fußzeile ist die Verwendung der **M_rectDraw** Mitglied [CPrintInfo](../mfc/reference/cprintinfo-structure.md). Jedes Mal, wenn eine Seite gedruckt wird, wird dieser Member mit dem verwendbaren Bereich der Seite initialisiert. Wenn Sie einer Kopf- oder Fußzeile vor dem Drucken der Hauptteil der Seite gedruckt werden, können Sie die Größe des Rechtecks in gespeicherten verringern **M_rectDraw** für den Bereich, die von der Kopf- oder Fußzeile zu berücksichtigen. Klicken Sie dann `OnPrint` können **M_rectDraw** herausfinden, wie viel Bereich bleibt für den Hauptteil der Seite zu drucken.

Sie können keinen Header oder etwas anderes, von Drucken [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc), da sie, bevor aufgerufen wird die `StartPage` Memberfunktion [CDC](../mfc/reference/cdc-class.md) aufgerufen wurde. Zu diesem Zeitpunkt gilt der Drucker-Gerätekontext an einer seitenbegrenzung werden. Durchführen können Drucken ausschließlich über den `OnPrint` Member-Funktion.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Drucken von mehrseitige Dokumenten](../mfc/multipage-documents.md)

- [Zuordnen von GDI-Ressourcen für Drucken](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>Siehe auch

[Drucken](../mfc/printing.md)
