---
title: 'OLE-Hintergrund: Verlinken und einbetten'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
ms.openlocfilehash: 02607df2a8fa086c5751f2b446e349a3efdbcd20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186801"
---
# <a name="ole-background-linking-and-embedding"></a>OLE-Hintergrund: Verlinken und einbetten

Verwenden den Befehl "Einfügen" in einer containeranwendung kann eine embedded-Komponente oder ein eingebettetes Element erstellt. Die Quelldaten für ein eingebettetes Element werden als Teil des OLE-Dokuments gespeichert, die sie enthält. Auf diese Weise wird eine Dokumentdatei für ein Textverarbeitungsdokument kann Text enthalten, und Sie dürfen auch Bitmaps, Diagramme, Formeln oder einen anderen Typ von Daten.

OLE stellt eine andere Möglichkeit, Daten aus einer anderen Anwendung zu integrieren: Erstellen einer verknüpften Komponente, oder verknüpftes Element oder ein Link. Die Schritte zum Erstellen eines verknüpften Elements ähneln denen zum Erstellen eines eingebetteten Elements, außer dass Sie die Verknüpfung einfügen-Befehl, anstatt den Befehl "Einfügen verwenden". Im Gegensatz zu einer embedded-Komponente speichert eine verknüpfte Komponente einen Pfad zu die ursprünglichen Daten, die häufig in einer separaten Datei ist.

Wenn Sie in einem Wort Prozessor Dokument arbeiten und ein verknüpftes Element, um einige Tabellenzellen zu erstellen, werden z. B. die Daten für das verknüpfte Element im ursprünglichen Arbeitsblatt-Dokument gespeichert. Das Textverarbeitungsdokument enthält nur die Informationen, die angeben, in dem das Element, d. h. gefunden werden können sie einen Link zum ursprünglichen Arbeitsblatt Dokument enthält. Wenn Sie die Zellen doppelklicken, die Arbeitsblatt-Anwendung wird gestartet, und das ursprüngliche Arbeitsblatt-Dokument aus, wo sie gespeichert wurde geladen.

Alle OLE-Element weist, ob eingebettete oder verknüpfte, den Typ zugeordneten basierend auf der Anwendung, die sie erstellt haben. Z. B. ein Microsoft Paintbrush-Element ist eine Art von Element, und ein Microsoft Excel-Element ist eine andere Art. Einige Anwendungen können jedoch mehr als einem Elementtyp erstellen. Beispielsweise können Sie mit Microsoft Excel Arbeitsblatt Elemente, Diagrammelemente und Makro wurde Elemente erstellen. Jedes dieser Elemente kann eindeutig identifizieren, wenn das System über eine Klassen-ID oder **CLSID**.

## <a name="see-also"></a>Siehe auch

[OLE-Hintergrund](../mfc/ole-background.md)<br/>
[OLE-Hintergrund: Container und Server](../mfc/ole-background-containers-and-servers.md)<br/>
[Container: Clientelemente](../mfc/containers-client-items.md)<br/>
[Server: Serverelemente](../mfc/servers-server-items.md)
