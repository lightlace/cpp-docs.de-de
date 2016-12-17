---
title: "ATL-Auflistungsklassen"
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
  - "Auflistungsklassen"
  - "Auflistungsklassen, Informationen über Auflistungsklassen"
  - "Auflistungsklassen, Auswählen"
  - "ConstructElements-Funktion"
  - "CTraits-Klassen"
  - "DestructElements-Funktion"
  - "SerializeElements-Funktion"
  - "Traits-Klassen"
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Auflistungsklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL stellt viele Klassen zum Speichern und Zugreifen auf von Daten bereit.  Welche Klasse, wenn Sie verwenden, hängt von mehreren Faktoren ab und enthält:  
  
-   Die Menge von den zu speichernden Daten  
  
-   Effizienz und Leistung, wenn auf die Daten zugegriffen werden  
  
-   Die Fähigkeit, auf die Daten nach Index oder nach Schlüssel zuzugreifen  
  
-   Wie die Daten sortiert werden  
  
-   Persönliche Einstellung  
  
## Kleine Auflistungsklassen  
 ATL stellt die folgenden Arrayklassen zur Handhabung von einer kleinen Anzahl Objekte bereit.  Allerdings werden diese Klassen für die Verwendung intern von ATL beschränkt und vorgesehen.  Es wird nicht empfohlen, sie in Programmen verwenden.  
  
|Klasse|Typ der Datenspeicherung|  
|------------|------------------------------|  
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Implementiert eine Array\-Klasse zur Handhabung von einer kleinen Anzahl Objekte.|  
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Implementiert eine Assoziationsklasse zur Handhabung von einer kleinen Anzahl Objekte.|  
  
## Universelle Auflistungsklassen  
 Die Folgungsklassen implementieren Arrays, Listen und Zuordnungen und werden als universelle Auflistungsklassen bereitgestellt:  
  
|Klasse|Typ der Datenspeicherung|  
|------------|------------------------------|  
|[CAtlArray](../atl/reference/catlarray-class.md)|Implementiert ein Array.|  
|[CAtlList](../atl/reference/catllist-class.md)|Implementiert eine Liste.|  
|[CAtlMap](../atl/reference/catlmap-class.md)|Implementiert eine Zuordnungsstruktur, wobei Daten über einen Schlüssel oder Wert verwiesen werden kann.|  
|[CRBMap](../atl/reference/crbmap-class.md)|Implementiert eine Zuordnungsstruktur mithilfe des RED\-Schwarz Algorithmus.|  
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Implementiert eine RED\-Schwarz multimapping Struktur.|  
  
 Diese Klassen werden viele Programmierfehler auf, wenn sie in Debugbuilds verwendet werden, jedoch für Grund der Leistung, werden diese Überprüfungen nicht in den Verkaufsversionsbuildern ausgeführt.  
  
## Spezialisierte Auflistungsklassen  
 Weitere spezialisiertere Auflistungsklassen werden auch zum Verwalten von Speicherzeigern und von Schnittstellenzeigern bereitgestellt:  
  
|Klasse|Zweck|  
|------------|-----------|  
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Stellt die Methoden bereit, die hilfreich sind, wenn ein Array intelligenten Zeiger.|  
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Stellt die Methoden bereit, die hilfreich sind, wenn, eine Liste von intelligenten Zeiger.|  
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|Speichert `IUnknown` Zeiger und sind so konzipiert, als Parameter an die [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse verwendet werden.|  
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Stellt die Methoden bereit, die hilfreich sind, wenn, eine Liste von Heapzeigern.|  
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|Stellt die Methoden bereit, die hilfreich sind, wenn ein Array COM\-Schnittstellenzeiger.|  
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|Stellt die Methoden bereit, die hilfreich sind, wenn, eine Liste von COM\-Schnittstellenzeigern.|  
  
## Auswählen einer Auflistungsklasse  
 Jede der verfügbaren Auflistungsklassen bietet verschiedene Leistungsmerkmale, wie in der Tabelle unten an.  
  
-   2 Spalten und 3 beschreiben die Reihenfolge einer Klasse und greifen auf Eigenschaften zu.  In der Tabelle "bestellte der Begriff" bedeutet, dass die Reihenfolge, in der Elemente eingefügt und gelöscht werden, deren Reihenfolge in der Auflistung bestimmt; Dies bedeutet nicht, dass die Elemente auf ihren Inhalt angepasst werden.  Der Begriff "indizierte" bedeutet, dass die Elemente in der Auflistung mit einem ganzzahligen Index abgerufen werden können, ähnlich wie Elemente in einem typischen Array.  
  
-   4 Spalten und 5 beschreiben die Leistung jeder Klasse.  In Anwendungen, die viele Einfügungen in die Auflistung benötigen, kann Einfügungsgeschwindigkeit besonders wichtig; für andere Anwendungen ist möglicherweise Suchengeschwindigkeit wichtiger.  
  
-   Spalte 6 beschreibt, ob jeder Form doppelte Elemente zulässig.  
  
-   Die Leistung eines angegebenen Auflistungsklassenvorgangs wird im Hinblick auf die Beziehung zwischen der Zeit ausgedrückt, die erforderlich ist, um den Vorgang und die Anzahl der Elemente in der Auflistung abzuschließen.  Ein Vorgang, der einen Zeitraum verwendet, die sich linear erhöht, wenn die Anzahl der Elementzunahmen beschrieben wird als O \(n\) Algorithmus.  Im Gegensatz dazu ein Vorgang, der einen Zeitraum akzeptiert, der sich immer weiter erhöht, wenn die Anzahl der Elementzunahmen als O beschrieben wird \(Algorithmus des Protokolls n\).  Wenn im Hinblick auf Leistung, O \(n\) Protokollübertreffen Algorithmen an Leistung O \(n\) Algorithmen mehr und mehr, beispielsweise die Anzahl von Elementen zunimmt.  
  
### Auflistungs\-Form\-Funktionen  
  
|Form|Geordnet?|Indiziert?|Fügen Sie ein<br /><br /> element|Suche nach<br /><br /> angegebenes Element|Doppelt<br /><br /> Elemente?|  
|----------|---------------|----------------|-------------------------------|----------------------------------------|---------------------------|  
|List|Ja|Nein|Schnell \(konstante Zeit\)|Langsames O \(n\)|Ja|  
|Array|Ja|Durch int \(konstante Zeit\)|Verlangsamen Sie O \(n\), außer beim Einfügen am Ende, in diesem Fall konstant setzen Sie Zeit fest|Langsames O \(n\)|Ja|  
|Zuordnung|Nein|Durch Schlüssel \(konstante Zeit\)|Schnell \(konstante Zeit\)|Schnell \(konstante Zeit\)|Keine \(Schlüssel\) Ja \(Werte\)|  
|RED\-Schwarz Zuordnung|Ja \(über Schlüssel\)|Durch Schlüssel\-O \(log n\)|Schnelles O \(log n\)|Schnelles O \(log n\)|Nein|  
|RED\-Schwarz Multimap|Ja \(über Schlüssel\)|Durch Schlüssel\-O \(log n\) \(mehrere Werte pro Schlüssel\)|Schnelles O \(log n\)|Schnelles O \(log n\)|Ja \(mehrere Werte pro Schlüssel\)|  
  
## Verwenden CTraits\-Objekte  
 Während die ATL\-Auflistungsklassen verwendet werden können, um eine breite Palette von benutzerdefinierten Datentypen zu speichern, kann es nützlich sein, um, wichtige Funktionen wie Vergleiche zu überschreiben.  Wird mit der CTraits\-Klassen erreicht.  
  
 CTraits\-Klassen sind ähnlich, jedoch flexibler als, die MFC\-Auflistungsklassenhilfsfunktionen; [Hilfsfunktionen für die Auflistungsklasse](../mfc/reference/collection-class-helpers.md) finden Sie weitere Informationen.  
  
 Wenn Sie die entsprechende Auflistungsklasse erstellen, können Sie festlegen CTraits\-Klasse einer.  Diese Klasse enthält den Code, der Vorgänge wie Vergleiche ausführt, wenn er durch die anderen Methoden aufgerufen wird, die die Auflistungsklasse bilden.  Wenn das Listenobjekt eigene benutzerdefinierte Strukturen enthält, sollten Sie den Übereinstimmungstest neu definieren, um bestimmte Membervariablen nur zu vergleichen.  Auf diese Weise funktioniert die Listensuchenmethode des Objekts in einer wichtigsten Weise.  
  
## Beispiel  
  
### Code  
 [!CODE [NVC_ATL_Utilities#112](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#112)]  
  
## Kommentare  
 Eine Liste der CTraits\-Klassen, finden Sie unter [Auflistungsklassen](../atl/collection-classes.md).  
  
 Das folgende Diagramm zeigt die Klassenhierarchie für die CTraits\-Klassen an.  
  
 ![Merkmalhierarchie für Auflistungsklassen](../atl/media/vctraitscollectionclasseshierarchy.png "vcTraitsCollectionClassesHierarchy")  
  
## Auflistungsklassen\-Beispiele  
 Die folgenden Beispiele zeigen die Auflistungsklassen:  
  
-   [MMXSwarm\-Beispiel](../top/visual-cpp-samples.md)  
  
-   [DynamicConsumer\-Beispiel](../top/visual-cpp-samples.md)  
  
-   [UpdatePV\-Beispiel](../top/visual-cpp-samples.md)  
  
-   [Marquee\-Beispiel](../top/visual-cpp-samples.md)  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [Auflistungsklassen](../atl/collection-classes.md)