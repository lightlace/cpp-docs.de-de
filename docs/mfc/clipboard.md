---
title: Zwischenablage
ms.date: 11/04/2016
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
ms.openlocfilehash: 5814b2fdfc7fbcaca00037cc64dd71aa27d65cc3
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504612"
---
# <a name="clipboard"></a>Zwischenablage

In dieser Artikelreihe wird erläutert, wie Unterstützung für die Windows-Zwischenablage in MFC-Anwendungen implementieren. Die Windows-Zwischenablage wird auf zwei Arten verwendet:

- Implementierende standard Befehle im Menü Bearbeiten, z. B. Ausschneiden, kopieren und einfügen.

- Uniform Data implementieren, übertragen Sie mit Drag und drop (OLE).

Die Zwischenablage ist die standard-Windows-Methode der Übertragung von Daten zwischen einer Quelle und Ziel. Es kann auch in OLE-Operationen sehr nützlich sein. Durch die Einführung von OLE gibt es zwei Mechanismen der Zwischenablage in Windows. Der standardmäßigen Windows-Zwischenablage-API ist weiterhin verfügbar, aber es wurde mit der OLE-Datenübertragungsmechanismus ergänzt wurde. OLE einheitliche Datenübertragung (UDT) unterstützt, Ausschneiden, kopieren und Einfügen über die Zwischenablage, und ziehen und ablegen.

Die Zwischenablage ist ein Systemdienst, der von der gesamten Windows-Sitzung gemeinsam verwendet werden, damit sie nicht über ein Handle oder einer eigenen Klasse verfügt. Sie verwalten die Zwischenablage über Memberfunktionen der Klasse [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Verwenden des jeweiligen zwischenablagemechanismus](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [Mithilfe der herkömmlichen Windows-Zwischenablage-API](../mfc/clipboard-using-the-windows-clipboard.md)

- [Verwenden des OLE-zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)

- [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)

- [Die Windows-Zwischenablage](/windows/desktop/dataxchg/clipboard)

- [Implementieren von Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
