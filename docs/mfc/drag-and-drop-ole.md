---
title: Drag &amp; Drop (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
ms.openlocfilehash: 98bd58745e56a62bf5700e9b5fe4963a7b584953
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766799"
---
# <a name="drag-and-drop-ole"></a>Drag &amp; Drop (OLE)

Die Drag & Drop-Funktion von OLE ist in erster Linie eine Verknüpfung zum Kopieren und Einfügen von Daten. Wenn Sie die Zwischenablage kopieren oder Einfügen von Daten verwenden, sind eine Reihe von Schritten erforderlich. Sie wählen Sie die Daten, klicken Sie auf **Ausschneiden** oder **Kopie** aus der **bearbeiten** Menü verschieben in die Zieldatei, Fenster oder einer Anwendung, platzieren Sie den Cursor in den gewünschten Speicherort ein, und klicken Sie auf **Einfügen** aus der **bearbeiten** Menü.

OLE- Drag & Drop unterscheidet sich von dem Manager für Dateiserver-Drag & Drop-Mechanismus, der Dateinamen kann nur behandeln und dient speziell zum Dateinamen an Anwendungen übergeben. OLE- Drag & Drop ist wesentlich allgemeineren. Sie können Drag & drop-Daten, die auch in der Zwischenablage platziert werden konnte.

Bei Verwendung von OLE- Drag & Drop entfernt aus der Prozess zwei Schritte. Wählen Sie die Daten aus den Datenquellen-Fenster ("die Quelle"), ziehen Sie es auf das gewünschte Ziel (die "Drop Target"), und löschen sie die Maustaste loslassen. Der Vorgang entfällt die Notwendigkeit für Menüs und ist schneller als die Sequenz, kopieren und einfügen. Die einzige Voraussetzung ist, dass sowohl die Ziehquelle als auch das Ablageziel geöffnet und zumindest teilweise auf dem Bildschirm sichtbar sein müssen.

Verwenden OLE- Drag & Drop, können Daten von einem Speicherort zu einem anderen in einem Dokument, das zwischen verschiedenen Dokumenten oder zwischen Anwendungen übertragen werden. In einem Container oder einer Server-Anwendung implementiert werden kann, und jede Anwendung kann eine Drop-Quelle, Ziel eines Ablegevorgangs oder beides sein. Wenn eine Anwendung sowohl die Drop-Quelle als auch die Drop-Ziel unterstützt ist, ist Drag & Drop aktiviert zwischen untergeordneten Fenster oder in einem Fenster. Diese Funktion möglich Ihre Anwendung viel einfacher zu verwenden.

Wenn Sie nur die Drag & Drop-Funktionen von OLE verwenden möchten, finden Sie unter [Drag & Drop: Anpassen von](../mfc/drag-and-drop-customizing.md). In diesem Artikel erläuterten Techniken können zu nicht-OLE-Anwendungen, die Quellen zu löschen. Der Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../mfc/drag-and-drop-implementing-a-drop-target.md) beschreibt, wie Sie die Drop-Ziel-Unterstützung für OLE und nicht-OLE-Anwendungen zu implementieren. Es ist auch hilfreich sein, überprüfen Sie die MFC-OLE-Beispiele [OCLIENT](../overview/visual-cpp-samples.md) und [HIERSVR](../overview/visual-cpp-samples.md).

Wenn Sie nicht gelesen haben die [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md) Artikelreihe, Sie möchten dies jetzt nachzuholen. In diesen Artikeln wird erläutert, die Grundlagen von Datenübertragung und wie Sie es in Ihren Anwendungen implementieren.

Weitere Informationen zu Drag & Drop finden Sie unter:

- [Drag & Drop: Implementieren einer Drop-Quelle](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [Drag & Drop: Implementieren eines Drop-Ziels](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [Drag & Drop: Anpassen von](../mfc/drag-and-drop-customizing.md)

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)<br/>
[Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md)
