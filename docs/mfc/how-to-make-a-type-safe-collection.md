---
title: "Gewusst wie: Erstellen einer typsicheren Auflistung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Auflistungsklassen, Ableiten aus keiner Vorlage"
  - "Auflistungsklassen, Vorlagenbasiert"
  - "Auflistungsklassen, Typsicherheit"
  - "Serialisierung [C++], Auflistungsklassen"
  - "SerializeElements-Funktion"
  - "Serialisieren von Auflistungsklassenelementen"
  - "Typsichere Auflistungen"
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
caps.latest.revision: 10
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen einer typsicheren Auflistung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, wie Auflistungen für typsicheres eigener Datentypen macht.  Folgende Themen werden behandelt:  
  
-   [Verwenden von auf Vorlagen basierenden Typsicherheit für Klassen](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [Implementieren von Hilfsfunktionen](#_core_implementing_helper_functions)  
  
-   [Verwendung der nicht auf Vorlagen basierenden Auflistungsklassen](#_core_using_nontemplate_collection_classes)  
  
 Die Microsoft Foundation Class\-Bibliothek stellt vordefinierte typsichere Auflistungen auf Grundlage C\+\+\-Vorlagen bereit.  Da von Vorlagen sind, unterstützen diese Klassen, die Typsicherheit und Benutzerfreundlichkeit ohne die angegebene Typumwandlung und weitere Aufgaben bereitzustellen, wenn es für diesen Zweck eine nicht auf Vorlagen basierende Klassen beteiligte, verwenden.  Das MFC\-Beispiel [COLLECT Sie](../top/visual-cpp-samples.md) veranschaulicht die Verwendung von auf Vorlagen basierenden Auflistungsklassen in einer MFC\-Anwendung.  Im Allgemeinen verwenden Sie diese Klassen, wenn Sie neuen Auflistungscode schreiben.  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> Verwenden von auf Vorlagen basierenden Typsicherheit für Klassen  
  
#### So auf Vorlagen basierende Klassen verwenden  
  
1.  Deklarieren Sie eine Variable des Auflistungsklassentyps.  Beispiel:  
  
     [!CODE [NVC_MFCCollections#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#7)]  
  
2.  Rufen Sie die Memberfunktionen des Auflistungsobjekts auf.  Beispiel:  
  
     [!CODE [NVC_MFCCollections#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#8)]  
  
3.  Falls notwendig implementieren Sie unter [Hilfsfunktionen](../mfc/reference/collection-class-helpers.md) und [SerializeElements](../Topic/SerializeElements.md).  Informationen zum Implementieren dieser Funktionen, finden Sie unter [Implementieren von Hilfsfunktionen](#_core_implementing_helper_functions).  
  
 In diesem Beispiel wird die Deklaration einer Liste von ganzen Zahlen.  Der erste Parameter im Schritt 1 ist der Typ der Daten, die als Elemente der Liste gespeichert werden.  Gibt der zweite Parameter an, wie die Daten übergeben werden und von Memberfunktionen der Auflistungsklasse, wie **Hinzufügen** und `GetAt` zurückgegeben werden sollen.  
  
##  <a name="_core_implementing_helper_functions"></a> Implementieren von Hilfsfunktionen  
 Die Vorlage gebildeten Auflistungsklassen `CArray`, `CList` und globale Hilfsfunktionen `CMap` mit fünf, die Sie für die abgeleitete Auflistungsklasse nach Bedarf anpassen können.  Informationen zu diesen Hilfsfunktionen, finden Sie unter [Auflistungsklassen\-Hilfen](../mfc/reference/collection-class-helpers.md) in der *MFC\-Referenz*.  Implementierung der Serialisierungsfunktionen ist für die meisten Anwendungen von den vorlagenbasierten Auflistungsklassen erforderlich.  
  
###  <a name="_core_serializing_elements"></a> Serialisieren von Elementen  
 `CArray`, `CList` und `CMap`\-Klassen rufen `SerializeElements` auf, um Elemente zu speichern oder sie in einem Archiv zu lesen.  
  
 Die Standardimplementierung der `SerializeElements` \- Hilfsfunktion führt eine bitweise Schreiben von Objekten dem Archiv oder einem bitweisen Lesen aus dem Archiv auf Objekte, abhängig davon, ob die Objekte gespeichert werden oder dem Archiv abgerufen.  Überschreiben Sie `SerializeElements`, wenn diese Aktion nicht geeignet ist.  
  
 Wenn die Auflistung Objekte gespeichert, die von `CObject` abgeleitet werden und Sie das `IMPLEMENT_SERIAL`\-Makro in der Implementierung der Auflistungselementklasse verwenden, können Sie die Serialisierungsfunktionalität nutzen, die in `CArchive` und `CObject` erstellt wird:  
  
 [!CODE [NVC_MFCCollections#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#9)]  
  
 Die überladenen Einfügungsoperatoren für `CArchive` rufen `CObject::Serialize` \(oder eine Überschreibung der Funktion\) für jedes **CPerson**\-Objekt auf.  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> Verwendung der nicht auf Vorlagen basierenden Auflistungsklassen  
 MFC unterstützt auch die Auflistungsklassen, die mit MFC 1.0.  Diese Klassen sind nicht basierend auf Vorlagen.  Sie können verwendet werden, um Daten der unterstützten Typen `CObject*`, **UINT**, `DWORD` und `CString` enthalten.  Sie können diese vordefinierten Auflistungen verwenden \(wie `CObList`\) um Auflistungen alle Objekte enthalten, die von `CObject` abgeleitet werden.  MFC stellt auch weitere vordefinierte Auflistungen, die primitive Typen wie **UINT** und void\-Zeiger \(`void`\*\) aufzunehmen.  Im Allgemeinen ist es jedoch oft hilfreich, typsicheren eigene Auflistungen definieren, um Objekte eine spezifischere Klasse und ihre Ableitungen aufzunehmen.  Beachten Sie, dass so mit den Auflistungsklassen nicht basierend auf Vorlagen vorhanden, ist mehr Arbeit als die Verwendung der vorlagenbasierten Klassen.  
  
 Es gibt zwei Möglichkeiten, typsichere Auflistungen mit den nicht vorlagenbasierten Auflistungen erstellen:  
  
1.  Verwenden Sie die nicht vorlagenbasierten Auflistungen, mit durch Typumwandlung.  Dies ist der einfacheren Ansatz.  
  
2.  Sind von und erweitern Sie eine nicht auf Vorlagen basierende typsichere Auflistung.  
  
#### Um die nicht vorlagenbasierten Auflistungen mit Typumwandlung verwenden  
  
1.  Verwenden Sie eine der nicht auf Vorlagen basierenden Klassen, wie `CWordArray`, direkt.  
  
     Beispielsweise können Sie ein `CWordArray` erstellen und alle 32\-Bit\-Werten hinzufügen, und rufen sie ab.  Es gibt keine weitere Vorteile.  Sie verwenden nur die vordefinierte Funktionen.  
  
     Sie können eine vordefinierte Auflistung, z `CObList` auch verwenden, um alle Objekte aufzunehmen wird von `CObject` abgeleitet.  Eine `CObList`\-Auflistung wird definiert, um Zeiger auf `CObject` enthält.  Wenn Sie ein Objekt aus der Liste abrufen, müssen Sie möglicherweise das Ergebnis den richtigen Typ umwandeln, da die Funktionen `CObList` Zeiger auf `CObject` zurückgeben.  Wenn Sie `CPerson`\-Objekte in einer `CObList`\-Auflistung speichern, müssen Sie ein abgerufenes Element umwandeln, um ein Zeiger auf ein `CPerson`\-Objekt sein.  Im folgenden Beispiel wird eine `CObList`\-Auflistung, um `CPerson`\-Objekte enthalten:  
  
     [!CODE [NVC_MFCCollections#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#10)]  
  
     Diese Technik einen vordefinierten Auflistungstyp ggf. aus verwenden und von umwandeln kann für viele der Auflistungsanforderungen geeignet.  Wenn Sie weitere Funktionalität oder mehr Typsicherheit benötigen, verwenden Sie eine Vorlage gebildete Klasse, oder halten Sie die folgende Prozedur ein.  
  
#### Um eine nicht auf Vorlagen basierende typsichere Auflistung ableiten und erweitern  
  
1.  Leiten Sie eine eigene Auflistungsklasse aus einer der vordefinierten nicht auf Vorlagen basierenden Klassen.  
  
     Wenn Sie eine Klasse ableiten, können Sie typsichere Wrapperfunktionen hinzufügen, um eine typsichere Schnittstelle zu vorhandenen Features bereitzustellen.  
  
     Wenn Sie eine Liste von `CObList` ableiten, um `CPerson`\-Objekte enthält, könnten Sie die Wrapperfunktionen `AddHeadPerson` und `GetHeadPerson`, wie unten dargestellt hinzugefügt.  
  
     [!CODE [NVC_MFCCollections#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#11)]  
  
     Diese Wrapperfunktionen stellen eine typsichere Weise, `CPerson`\-Objekten von der abgeleiteten Liste hinzuzufügen und abzurufen.  Sie können sehen, dass die Funktion für `GetHeadPerson`, Sie einfach die Typumwandlung kapseln.  
  
     Sie können auch neue Funktionen hinzufügen, indem Sie neue Funktionen definieren, die die Leistungsfähigkeit der Auflistung statt vorhandene Funktionen erweitern in den typsicheren Wrappern nur, einbindend.  Zum Beispiel beschreibt der Artikel [Löschen aller Objekte in einer CObject\-Auflistung](../mfc/deleting-all-objects-in-a-cobject-collection.md) eine Funktion, um alle Objekte zu löschen, die in einer Liste enthalten sind.  Diese Funktion kann zur abgeleiteten Klasse als Memberfunktion hinzugefügt werden.  
  
## Siehe auch  
 [Auflistungen](../mfc/collections.md)