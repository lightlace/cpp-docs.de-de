---
title: 'Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
ms.openlocfilehash: d8ef93b306c0968adf2c23c841c792d2f7af5de3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327041"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus

OLE verwendet standard-Formate und einige spezifische OLE-Formate für die Übertragung von Daten über die Zwischenablage.

Wenn Sie Ausschneiden oder Kopieren von Daten aus einer Anwendung, ist die Daten in die Zwischenablage, die weiter unten in der Einfügevorgänge verwendet werden gespeichert. Diese Daten sind in einer Vielzahl von Formaten. Wenn ein Benutzer auswählt, um Daten aus der Zwischenablage einzufügen, können die Anwendung die der folgenden Formate verwenden. Wählen Sie das Format, die meisten Informationen bereitstellen, es sei denn, der speziell für ein bestimmtes Format Frage mit Inhalte einfügen, sollte die Anwendung geschrieben werden. Bevor Sie fortfahren, sollten Sie zum Lesen der [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md) Themen. Beschreiben sie die Grundlagen der wie von Datenübertragungen, und wie Sie diese in Ihren Anwendungen implementieren.

Windows definiert eine Anzahl von standard-Formate, die zum Übertragen von Daten über die Zwischenablage verwendet werden können. Dazu gehören Metadateien, Bitmaps, Text und andere. OLE wird eine Anzahl von OLE-spezifische Formate, ebenfalls definiert. Für Anwendungen, die mehr Details als Angabe durch diese Standardformate benötigen, ist es ratsam, eigene benutzerdefinierte Zwischenablageformate registriert. Verwenden Sie die Win32-API-Funktion [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) dazu.

Microsoft Excel wird beispielsweise ein benutzerdefiniertes Format für Tabellen registriert. Dieses Format enthält, weit mehr Informationen als z. B., eine Bitmap ist. Wenn diese Daten in eine Anwendung, die das Arbeitsblattformat unterstützt eingefügt werden, werden alle Formeln und Werte aus dem Arbeitsblatt werden beibehalten und können bei Bedarf aktualisiert werden. Microsoft Excel überträgt Daten in der Zwischenablage in Formaten, damit sie als OLE-Element eingefügt werden können. Alle OLE-Document-Container kann diese Informationen als eingebettetes Element einfügen. Diese eingebetteten Elements kann mithilfe von Microsoft Excel geändert werden. Die Zwischenablage enthält auch eine einfache Bitmap des Bilds des ausgewählten Bereichs in der Kalkulationstabelle. Dies kann auch in OLE-Document-Container oder in Bitmap-Editor wie Paint eingefügt werden. Für eine Bitmap allerdings besteht keine Möglichkeit, die Daten als Tabelle zu bearbeiten.

Um die maximale Menge an Informationen aus der Zwischenablage abzurufen, sollten Anwendungen für diese benutzerdefinierte Formate überprüfen, bevor Sie die Daten aus der Zwischenablage einfügen.

Beispielsweise können damit kann der Befehl "Ausschneiden", Sie einen Handler etwa wie folgt schreiben:

[!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)

- [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)

- [Verwenden der Windows-Zwischenablage](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE](../mfc/ole-background.md)

- [OLE-Objekte und Daten-Datenquellen und einheitliche Datenübertragung](../mfc/data-objects-and-data-sources-ole.md)

## <a name="see-also"></a>Siehe auch

[Zwischenablage](../mfc/clipboard.md)
