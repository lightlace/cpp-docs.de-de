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
ms.openlocfilehash: d405a7bbe15d2658380e19c1c908e57f2e40a574
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508929"
---
# <a name="clipboard"></a>Zwischenablage

In dieser Artikel Familie wird erläutert, wie die Unterstützung für die Windows-Zwischenablage in MFC-Anwendungen implementiert wird. Die Windows-Zwischenablage wird auf zweierlei Weise verwendet:

- Implementieren von Standard Befehlen zum Bearbeiten von Menüs, z. b. Ausschneiden, kopieren und einfügen.

- Implementieren von einheitlicher Datenübertragung mit Drag & Drop (OLE).

Die Zwischenablage ist die standardmäßige Windows-Methode zum Übertragen von Daten zwischen einer Quelle und einem Ziel. Dies kann auch bei OLE-Vorgängen sehr nützlich sein. Mit der Einführung von OLE gibt es zwei Zwischenablage Mechanismen in Windows. Die standardmäßige Windows-Zwischenablage-API ist weiterhin verfügbar, wurde jedoch mit dem OLE-Datenübertragungsmechanismus ergänzt. OLE Uniform Data Transfer (UDT) unterstützt Ausschneiden, kopieren und Einfügen mit der Zwischenablage und Drag & Drop.

Die Zwischenablage ist ein Systemdienst, der von der gesamten Windows-Sitzung gemeinsam verwendet wird, sodass Sie nicht über ein Handle oder eine eigene Klasse verfügt. Sie verwalten die Zwischenablage mithilfe von Element Funktionen der [CWnd](../mfc/reference/cwnd-class.md)-Klasse.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Verwendung der einzelnen Zwischenablage Mechanismen](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [Verwenden der herkömmlichen Windows-Zwischenablage-API](../mfc/clipboard-using-the-windows-clipboard.md)

- [Verwenden des OLE-Zwischenablage Mechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)

- [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)

- [Die Windows-Zwischenablage](/windows/win32/dataxchg/clipboard)

- [Implementieren von Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
