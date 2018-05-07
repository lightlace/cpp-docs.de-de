---
title: 'Datenobjekte und Datenquellen: Bearbeitung | Microsoft Docs'
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
ms.openlocfilehash: b4c3414734f40ee81689ffa2f160cbbab8306d2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-objects-and-data-sources-manipulation"></a>Datenobjekte und Datenquellen: Bearbeitung
Nach einem Datenobjekt oder die Datenquelle erstellt wurde, können Sie diverse häufig verwendeter Vorgänge auf die Daten, z. B. das Einfügen und Entfernen von Daten, die beim Aufzählen der Formate, denen die Daten in enthalten ist, und vieles mehr. Dieser Artikel beschreibt die Techniken zum Durchführen der am häufigsten verwendeten Vorgänge erforderlich sind. Folgende Themen werden behandelt:  
  
-   [Einfügen von Daten in einer Datenquelle](#_core_inserting_data_into_a_data_source)  
  
-   [Bestimmen die in einem Datenobjekt verfügbaren Formate](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [Abrufen von Daten aus einem Datenobjekt](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> Einfügen von Daten in einer Datenquelle  
 Wie die Daten in einer Datenquelle eingefügt werden, hängt gibt an, ob die Daten sofort bereitgestellt werden, oder bei Bedarf, und klicken Sie in das Medium wird bereitgestellt. Mögliche Werte sind wie folgt.  
  
### <a name="supplying-data-immediately-immediate-rendering"></a>Bereitstellen der Daten sofort (unmittelbares Rendern)  
  
-   Rufen Sie `COleDataSource::CacheGlobalData` wiederholt für jede Zwischenablageformat, in dem Sie Daten angegeben werden. Übergeben Sie das Format der Zwischenablage zu verwendende ein Handle für den Speicher, der Daten enthält und optional eine **FORMATETC** Struktur, die die Daten beschreibt.  
  
     - oder -   
  
-   Wenn Sie direkt mit arbeiten möchten **STGMEDIUM** Strukturen aus, und rufen Sie `COleDataSource::CacheData` anstelle von `COleDataSource::CacheGlobalData` in der oben genannten Option.  
  
### <a name="supplying-data-on-demand-delayed-rendering"></a>Bereitstellen der Daten bei Bedarf (verzögertes Rendering)  
 Dies ist ein-Thema für fortgeschrittene.  
  
-   Rufen Sie `COleDataSource::DelayRenderData` wiederholt für jede Zwischenablageformat, in dem Sie Daten angegeben werden. Übergeben Sie das Format der Zwischenablage verwendet werden und optional eine **FORMATETC** Struktur, die die Daten beschreibt. Wenn die Daten angefordert werden, ruft das Framework `COleDataSource::OnRenderData`, die Sie überschreiben müssen.  
  
     - oder -   
  
-   Bei Verwendung einer `CFile` die Daten zu verwendendes Objekt aufrufen `COleDataSource::DelayRenderFileData` anstelle von `COleDataSource::DelayRenderData` in der vorherigen Option. Wenn die Daten angefordert werden, ruft das Framework `COleDataSource::OnRenderFileData`, die Sie überschreiben müssen.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Bestimmen die in einem Datenobjekt verfügbaren Formate  
 Bevor eine Anwendung den Benutzer aus, um Daten in sie einzufügen zulässt, muss sie wissen, ob es Formate in der Zwischenablage, die er verarbeiten kann. Zu diesem Zweck sollten Ihre Anwendung die folgenden Schritte ausführen:  
  
1.  Erstellen einer `COleDataObject` Objekt und ein **FORMATETC** Struktur.  
  
2.  Rufen Sie des Datenobjekts `AttachClipboard` Memberfunktion versucht, ordnen Sie das Datenobjekt mit den Daten in die Zwischenablage.  
  
3.  Führen Sie einen der folgenden Schritte aus:  
  
    -   Rufen Sie des Datenobjekts `IsDataAvailable` Memberfunktion, wenn es nur eine oder zwei, die Sie Formate benötigen. Dadurch sparen Sie Zeit, in Fällen, in denen die Daten in der Zwischenablage deutlich mehr Formaten als die Anwendung unterstützt.  
  
         - oder -   
  
    -   Rufen Sie des Datenobjekts `BeginEnumFormats` Memberfunktion anfangen, der in der Zwischenablage verfügbaren Formate. Rufen Sie anschließend `GetNextFormat` bis Zwischenablage gibt ein Format auf die Anwendung unterstützt, oder es sind keine weitere Formate.  
  
 Bei Verwendung von `ON_UPDATE_COMMAND_UI`, Sie können jetzt das Einfügen und möglicherweise Inhalte einfügen Elemente im Menü Bearbeiten. Rufen Sie hierzu entweder `CMenu::EnableMenuItem` oder `CCmdUI::Enable`. Weitere Informationen zu welchem Container Anwendungen sollten mit Menüelementen wann sehen und [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md).  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> Abrufen von Daten aus einem Datenobjekt  
 Nachdem Sie ein Datenformat entschieden haben, übrig bleibt zum Abrufen der Daten aus dem Datenobjekt. Zu diesem Zweck der Benutzer entscheidet, die Daten eingefügt werden soll, und die Anwendung aufruft, die entsprechende Funktion. Die Daten in einem der folgenden Medien zur Verfügung:  
  
|Mittel|Funktion aufgerufen werden soll|  
|------------|----------------------|  
|Globaler Speicher (`HGLOBAL`)|`COleDataObject::GetGlobalData`|  
|Datei (`CFile`)|`COleDataObject::GetFileData`|  
|**STGMEDIUM** Struktur (`IStorage`)|`COleDataObject::GetData`|  
  
 Das Medium wird in der Regel zusammen mit seinem Zwischenablageformat angegeben werden. Z. B. eine **CF_EMBEDDEDSTRUCT** Objekt befindet sich immer in einer `IStorage` Medium, das erfordert eine **STGMEDIUM** Struktur. Verwenden Sie deshalb `GetData` , da es nur eine dieser Funktionen ist, akzeptieren, kann, ein **STGMEDIUM** Struktur.  
  
 Für Situationen, in denen das Format der Zwischenablage in eine `IStream` oder `HGLOBAL` Mittel, das Framework bieten eine `CFile` Zeiger, der die Daten verweisen. Die Anwendung kann dann verwenden, Datei, die gelesen, um die Daten im Wesentlichen die gleiche Weise abzurufen, wie sie Daten aus einer Datei importieren kann. Dies ist im Wesentlichen die Client-Side-Schnittstelle, um die `OnRenderData` und `OnRenderFileData` Routinen in der Datenquelle.  
  
 Der Benutzer kann sich nun in das Dokument von Daten für alle anderen Daten in das gleiche Format wie.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Drag & drop](../mfc/drag-and-drop-ole.md)  
  
-   [Zwischenablage](../mfc/clipboard.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject-Klasse](../mfc/reference/coledataobject-class.md)   
 [COleDataSource-Klasse](../mfc/reference/coledatasource-class.md)
