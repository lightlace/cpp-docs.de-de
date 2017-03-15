---
title: "Datenobjekte und Datenquellen: Bearbeitung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zwischenablage [C++], Feststellen verfügbarer Formate"
  - "Zwischenablage [C++], Weiterleiten von Formatinformationen"
  - "Datenobjekte [C++], Bearbeiten"
  - "Datenquellen [C++], Datenoperationen"
  - "Datenquellen [C++], Feststellen verfügbarer Formate"
  - "Datenquellen [C++], Einfügen von Daten"
  - "Verzögertes Rendering [C++]"
  - "OLE [C++], Datenobjekte"
  - "OLE [C++], Datenquellen"
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Datenobjekte und Datenquellen: Bearbeitung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nach einem Datenobjekt oder eine Datenquelle erstellt wurde, können Sie einige allgemeine Operationen mit den Daten, z Einfügen ausführen und die Daten entfernenden, Formate aufgelistet wird und die Daten sind in mehr.  In diesem Artikel werden die Techniken, die erforderlich sind, die am häufigsten verwendeten Vorgänge abzuschließen.  Folgende Themen werden behandelt:  
  
-   [Einfügen von Daten in einer Datenquelle](#_core_inserting_data_into_a_data_source)  
  
-   [Die Stile bestimmen verfügbar in einem Datenobjekt](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [Abrufen von Daten aus einem Datenobjekt](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> Einfügen von Daten in einer Datenquelle  
 Wie Daten in eine Datenquelle eingefügt werden, hängt davon ab, ob die Daten sofort oder bei Bedarf angegeben werden, und, in dem Medium dies angegeben wird.  Die Möglichkeiten sind wie folgt.  
  
### Daten direkt angeben \(direktes Rendering\)  
  
-   Rufen Sie für jedes `COleDataSource::CacheGlobalData` wiederholt Zwischenablageformat auf, in dem Sie Daten angeben.  Führen Sie, ein Handle für Speicher, der die Daten enthalten und optional mit einer **FORMATETC**\-Struktur verwendet werden Zwischenablageformat, die die Daten beschreiben.  
  
     \- oder \-  
  
-   Wenn Sie direkt mit **STGMEDIUM**\-Strukturen arbeiten möchten, rufen Sie `COleDataSource::CacheData` statt `COleDataSource::CacheGlobalData` in der Option oben auf.  
  
### Daten bei Bedarf angeben \(verzögertes Rendering\)  
 Dies ist ein fortgeschrittenes Thema.  
  
-   Rufen Sie für jedes `COleDataSource::DelayRenderData` wiederholt Zwischenablageformat auf, in dem Sie Daten angeben.  Führen Sie das zu verwendende Zwischenablageformat, und optional eine **FORMATETC**\-Struktur, die die Daten beschreiben.  Wenn die Daten angefordert wurden, ruft das Framework `COleDataSource::OnRenderData` auf, die Sie überschreiben müssen.  
  
     \- oder \-  
  
-   Wenn Sie ein `CFile`\-Objekt verwenden, um die Daten zu ermöglichen, rufen Sie `COleDataSource::DelayRenderFileData` statt `COleDataSource::DelayRenderData` in der vorherigen Option auf.  Wenn die Daten angefordert wurden, ruft das Framework `COleDataSource::OnRenderFileData` auf, die Sie überschreiben müssen.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Die Stile bestimmen verfügbar in einem Datenobjekt  
 Bevor eine Anwendung den Benutzern Pastendaten in sie auftreten können, muss es wissen, wenn Stile in der Zwischenablage sind, da behandeln kann.  Hierzu, sollte die Anwendung Folgendes durchführen:  
  
1.  Erstellen Sie ein `COleDataObject`\-Objekt und einer **FORMATETC**\-Struktur.  
  
2.  Rufen Sie die Memberfunktion `AttachClipboard` des Datenobjekts, auf das Datenobjekt mit den in der Zwischenablage Daten zuzuordnen.  
  
3.  Führen Sie eine der folgenden Aktionen aus:  
  
    -   Rufen Sie die Memberfunktion `IsDataAvailable` des Datenobjekts auf, wenn sich nur eine oder zwei Stile gibt, die Sie benötigen.  Dies speichert Sie Zeit, wenn die Daten in der Zwischenablage deutlich mehr Formate als Ihre Anwendung unterstützen.  
  
         \- oder \-  
  
    -   Rufen Sie die Memberfunktion `BeginEnumFormats` des Datenobjekts auf, um das Auflisten der Stile zu starten, die in der Zwischenablage sind verfügbar.  Rufen Sie anschließend `GetNextFormat` auf, bis die Zwischenablage ein Format Ihre Anwendungsunterstützung zurückgibt, oder nicht mehr gibt. Stile  
  
 Wenn Sie `ON_UPDATE_COMMAND_UI` verwenden, können Sie die Pasten\- und möglicherweise Inhalte einfügen\-Elemente im Menü Bearbeiten jetzt aktivieren.  Hierzu, rufen Sie `CMenu::EnableMenuItem` oder `CCmdUI::Enable` auf.  Weitere Informationen darüber, wodurch Containeranwendungen mit Menüelementen ratsam ist und wenn, finden Sie unter [Menüs und Ressourcen: Container\-Hinzufügungen](../mfc/menus-and-resources-container-additions.md).  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> Abrufen von Daten aus einem Datenobjekt  
 Sobald Sie auf einen Datenformat festlegen, ist der gesamte, bleibt der, die Daten vom Datenobjekt abzurufen.  Hierzu, entscheidet der Benutzer wo die Daten und die Anwendung die entsprechende Funktion wird.  Die Daten in einem der folgenden Medien verfügbar:  
  
|Mittel|Aufzurufende Funktion|  
|------------|---------------------------|  
|Globaler Arbeitsspeicher \(`HGLOBAL`\)|`COleDataObject::GetGlobalData`|  
|Datei \(`CFile`\)|`COleDataObject::GetFileData`|  
|**STGMEDIUM**\-Struktur \(`IStorage`\)|`COleDataObject::GetData`|  
  
 Häufig wird der mittleren zusammen mit einem Zwischenablageformat angegeben.  Ein **CF\_EMBEDDEDSTRUCT**\-Objekt immer in einem `IStorage` Mediums, der eine **STGMEDIUM**\-Struktur erfordert.  Deshalb würden Sie `GetData` verwenden, da das einzige dieser Features ist, die eine **STGMEDIUM**\-Struktur akzeptieren können.  
  
 Für Fälle, in denen das Zwischenablageformat in einem `IStream` oder `HGLOBAL` Mittel ist, kann das Framework einen Zeiger `CFile` bereitstellen, der die Daten verwiesen wird.  Die Anwendung kann Datei dann verwenden, um die Daten abzurufen, ebenso wie sie ggf. Daten von einer Datei importiert werden.  Im Wesentlichen ist dies die clientseitige Schnittstelle mit den `OnRenderData` und `OnRenderFileData` Routinen in der Datenquelle.  
  
 Der Benutzer kann Daten in das Dokument genauso wie für andere Daten im gleichen Format jetzt einfügen.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Per Drag & Drop](../mfc/drag-and-drop-ole.md)  
  
-   [Zwischenablage](../mfc/clipboard.md)  
  
## Siehe auch  
 [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)