---
title: 'Datenobjekte und Datenquellen: Bearbeitung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5b44dd343c068a6a98765f9740dcd96b68bd323
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415491"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Datenobjekte und Datenquellen: Bearbeitung

Nach einer Datenquelle oder ein Datenobjekt, das erstellt wurde, können Sie eine Reihe allgemeiner Vorgänge für die Daten, z. B. einfügen und Entfernen von Daten, das Aufzählen von Formaten, ab die Daten in und vieles mehr ausführen. Dieser Artikel beschreibt die Techniken, die zum Abschließen der am häufigsten verwendeten Vorgänge erforderlich sind. Folgende Themen werden behandelt:

- [Einfügen von Daten in einer Datenquelle](#_core_inserting_data_into_a_data_source)

- [Bestimmen die Formate, die in einem Datenobjekt verfügbar](#_core_determining_the_formats_available_in_a_data_object)

- [Abrufen von Daten von einem Datenobjekt](#_core_retrieving_data_from_a_data_object)

##  <a name="_core_inserting_data_into_a_data_source"></a> Einfügen von Daten in einer Datenquelle

Hängt wie die Daten in einer Datenquelle eingefügt werden, ob die Daten sofort bereitgestellt werden, oder bei Bedarf, und klicken Sie in der mittleren ist er bereitgestellt. Mögliche Werte sind wie folgt aus.

### <a name="supplying-data-immediately-immediate-rendering"></a>Sofortiges Bereitstellen der Daten (unmittelbares Rendern)

- Rufen Sie `COleDataSource::CacheGlobalData` wiederholt für jede Zwischenablageformat, in dem Sie Daten angegeben werden. Übergeben Sie das Format der Zwischenablage verwendet werden, ein Handle für den Arbeitsspeicher mit den Daten und optional eine **FORMATETC** Struktur, die die Daten beschreibt.

     - oder - 

- Wenn Sie direkt mit arbeiten möchten **STGMEDIUM** Strukturen die, Sie aufrufen `COleDataSource::CacheData` anstelle von `COleDataSource::CacheGlobalData` in der oben genannten Option.

### <a name="supplying-data-on-demand-delayed-rendering"></a>Bereitstellen von Daten bei Bedarf (verzögertes Rendering)

Dies ist ein Thema für fortgeschrittene.

- Rufen Sie `COleDataSource::DelayRenderData` wiederholt für jede Zwischenablageformat, in dem Sie Daten angegeben werden. Übergeben Sie das Format der Zwischenablage verwendet werden und optional eine **FORMATETC** Struktur, die die Daten beschreibt. Wenn die Daten angefordert werden, ruft das Framework `COleDataSource::OnRenderData`, die Sie überschreiben müssen.

     - oder - 

- Bei Verwendung einer `CFile` die Daten zu verwendendes Objekt aufrufen `COleDataSource::DelayRenderFileData` anstelle von `COleDataSource::DelayRenderData` in der vorherigen Option. Wenn die Daten angefordert werden, ruft das Framework `COleDataSource::OnRenderFileData`, die Sie überschreiben müssen.

##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Bestimmen die Formate, die in einem Datenobjekt verfügbar

Bevor eine Anwendung auf der Benutzer Daten in diese einfügen kann, muss sie wissen, ob Formate vorliegen, in der Zwischenablage an, die er verarbeiten kann. Zu diesem Zweck sollte die Anwendung folgendermaßen vor:

1. Erstellen Sie eine `COleDataObject` Objekt und ein **FORMATETC** Struktur.

1. Rufen Sie des Datenobjekts `AttachClipboard` Memberfunktion, die Daten in der Zwischenablage das Datenobjekt zugeordnet werden soll.

1. Führen Sie einen der folgenden Schritte aus:

   - Rufen Sie des Datenobjekts `IsDataAvailable` Memberfunktion, wenn es nur eine oder zwei, die Sie Formate benötigen. Dadurch sparen Sie Zeit, in Fällen, in denen die Daten in die Zwischenablage deutlich mehr Formaten als Ihrer Anwendung unterstützt.

         -or-

   - Rufen Sie des Datenobjekts `BeginEnumFormats` Memberfunktion versucht, mit dem Aufzählen von die Formate, die in der Zwischenablage verfügbar sind. Rufen Sie anschließend `GetNextFormat` bis zurückgegeben von die Zwischenablage ein Format Ihrer Anwendung unterstützt, oder es sind keine weitere Formate.

Bei Verwendung von **ON_UPDATE_COMMAND_UI**, Sie können jetzt das Einfügen und möglicherweise Inhalte einfügen Elemente auf das Menü "Bearbeiten" aktivieren. Zu diesem Zweck rufen Sie entweder `CMenu::EnableMenuItem` oder `CCmdUI::Enable`. Weitere Informationen über welche Container Anwendungen sollten mit Menüelementen und, [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md).

##  <a name="_core_retrieving_data_from_a_data_object"></a> Abrufen von Daten von einem Datenobjekt

Wenn Sie auf ein Format entschieden haben, übrig bleibt zum Abrufen der Daten aus dem Datenobjekt. Zu diesem Zweck der Benutzer entscheidet, wo die Daten abgelegt werden sollen, und die Anwendung ruft die entsprechende Funktion. Die Daten werden in einem der folgenden Medien zur Verfügung:

|Mittel|Funktion aufrufen|
|------------|----------------------|
|Globaler Speicher (`HGLOBAL`)|`COleDataObject::GetGlobalData`|
|Datei (`CFile`)|`COleDataObject::GetFileData`|
|**STGMEDIUM** Struktur (`IStorage`)|`COleDataObject::GetData`|

Das Medium wird normalerweise zusammen mit der das Format der Zwischenablage angegeben werden. Z. B. eine **CF_EMBEDDEDSTRUCT** Objekt befindet sich immer im eine `IStorage` Medium, das erfordert eine **STGMEDIUM** Struktur. Verwenden Sie daher `GetData` , da es die einzige dieser Funktionen ist, den annehmen kann ein **STGMEDIUM** Struktur.

Für Situationen, in dem das Format der Zwischenablage in eine `IStream` oder `HGLOBAL` Medium das Framework bieten eine `CFile` Zeiger, der die Daten verweisen. Die Anwendung können Sie dann die Datei gelesen, um die Daten im Wesentlichen die gleiche Weise abzurufen, wie sie Daten aus einer Datei importieren kann. Im Wesentlichen ist dies die Client-Side-Schnittstelle, um die `OnRenderData` und `OnRenderFileData` Routinen in der Datenquelle.

Der Benutzer kann jetzt Einfügen von Daten in das Dokument nur für alle anderen Daten in das gleiche Format wie an.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Drag & drop](../mfc/drag-and-drop-ole.md)

- [Zwischenablage](../mfc/clipboard.md)

## <a name="see-also"></a>Siehe auch

[Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject-Klasse](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource-Klasse](../mfc/reference/coledatasource-class.md)
