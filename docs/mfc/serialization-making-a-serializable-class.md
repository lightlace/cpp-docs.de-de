---
title: "Serialisierung: Erstellen einer serialisierbaren Klasse | Microsoft Docs"
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
  - "Klassen [C++], Abgeleitet"
  - "CObject-Klasse, Abgeleitete serialisierbare Klassen"
  - "Konstruktoren [C++], Definieren ohne Argumente"
  - "DECLARE_SERIAL-Makro"
  - "Standardkonstruktor"
  - "Standardwerte [C++], Konstruktor"
  - "IMPLEMENT_SERIAL-Makro"
  - "Kein Standardkonstruktor"
  - "no-arguments-Konstruktor"
  - "Serialisierbare Klasse"
  - "Serialisierung [C++], Serialisierbare Klassen"
  - "Serialize-Methode, Überschreiben"
  - "VERSIONABLE_SCHEMA-Makro"
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Serialisierung: Erstellen einer serialisierbaren Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fünf Hauptschritte sind erforderlich, um eine Klasse serialisierbar zu machen.  Sie sind nachfolgend aufgeführt und erläutert in den folgenden Abschnitten:  
  
1.  [Ableiten der Klasse von CObject](#_core_deriving_your_class_from_cobject) \(oder von einer Klasse abgeleitet von `CObject`\).  
  
2.  [Überschreiben der serialisierensmemberfunktion](#_core_overriding_the_serialize_member_function).  
  
3.  [Verwenden des DECLARE\_SERIAL\-Makros](#_core_using_the_declare_serial_macro) in der Klassendeklaration.  
  
4.  [Ein Konstruktor definieren, der keine Argumente akzeptiert](#_core_defining_a_constructor_with_no_arguments).  
  
5.  [Verwenden des IMPLEMENT\_SERIAL\-Makros in der Implementierungsdatei](#_core_using_the_implement_serial_macro_in_the_implementation_file) für die Klasse.  
  
 Wenn Sie `Serialize` direkt anstatt von Operatoren und \>\> \<\< von [CArchive](../mfc/reference/carchive-class.md) aufrufen, werden die letzten drei Schritte nicht für Serialisierung erforderlich.  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> Ableiten der Klasse von CObject  
 Das grundlegende Serialisierungsprotokoll und Funktionen werden in der `CObject`\-Klasse definiert.  Indem Sie die Klasse von `CObject` \(oder einer Klasse abgeleitet von `CObject`\), wie in der folgenden Deklaration der Klasse `CPerson` angezeigt werden, rufen Sie den Serialisierungsprotokoll und die Funktionalität von `CObject` zugreifen.  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> Überschreiben der serialisierens\-Memberfunktion  
 Die Memberfunktion `Serialize`, die in der `CObject`\-Klasse definiert ist, ist für die Daten tatsächlich serialisieren zuständig, die erforderlich sind, um den aktuellen Zustand eines Objekts aufzuzeichnen.  Die Funktion `Serialize` verfügt über ein Argument `CArchive`, das verwendet, die zum Lesen und schreibt die Objektdaten.  [CArchive](../mfc/reference/carchive-class.md) Das Objekt verfügt über eine Memberfunktion, `IsStoring`, die angibt, ob `Serialize` speichert \(Protokoll\) oder \(Laden Lesendaten\).  Verwenden der `IsStoring` Ergebnisse als Leitfaden, fügen Sie entweder die Daten des Objekts im `CArchive`\-Objekt mit dem Einfügungsoperator \(**\<\<**\) oder die Auszugdaten mit dem Extraktionsoperator ein \(**\>\>**\).  
  
 Erwägen Sie eine Klasse, die von `CObject` abgeleitet und zwei neue Membervariablen verfügt, Typen `CString` und **WORD**.  Im folgenden Klassendeklarationsfragment zeigt die neue Membervariablen und die Deklaration für die überschriebene `Serialize`\-Memberfunktion an:  
  
 [!CODE [NVC_MFCSerialization#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#1)]  
  
#### Um die serialisierensmemberfunktion überschreiben  
  
1.  Rufen Sie die Basisklassenversion von `Serialize` auf, um zu überprüfen, ob der geerbte Teil des Objekts serialisiert wird.  
  
2.  Einfügen oder Extrahieren Sie die Membervariablen, die der Klasse bestimmt sind.  
  
     Die Datensätze einfügen und Extraktionsoperatoren interagieren mit der Archivklasse, um die Daten zu lesen und zu schreiben.  Das folgende Beispiel zeigt, wie `Serialize` für die `CPerson`\-Klasse implementiert, die oben deklariert wird:  
  
     [!CODE [NVC_MFCSerialization#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#2)]  
  
 Sie können die [CArchive::Read](../Topic/CArchive::Read.md) und [CArchive::Write](../Topic/CArchive::Write.md)\-Memberfunktionen auch verwenden, um große Mengen der nicht typisierten Daten lesen und schreiben.  
  
##  <a name="_core_using_the_declare_serial_macro"></a> Verwenden des DECLARE\_SERIAL\-Makros  
 Das Makro ist `DECLARE_SERIAL` in der Deklaration von Klassen, die die Serialisierung unterstützen, wie hier gezeigt erforderlich:  
  
 [!CODE [NVC_MFCSerialization#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#3)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Definieren eines Konstruktor ohne Argumente  
 MFC benötigt einen Standardkonstruktor, wenn die Objekte erneut erstellt, die deserialisiert werden \(vom Datenträger geladen\).  Der Deserialisierungsprozess füllt alle Membervariablen mit den Werten aus, die erforderlich sind, das Objekt neu zu erstellen.  
  
 Dieser Konstruktor kann deklariert werden öffentlich, geschützt wurde, oder privat.  Wenn Sie ihn geschützt oder als privat machen, unterstützen Sie, sicherzustellen, dass er nur durch die Serialisierungsfunktionen verwendet wird.  Der Konstruktor muss das Objekt in einen Zustand versetzt werden, der bei Bedarf können gelöscht werden es.  
  
> [!NOTE]
>  Wenn Sie vergessen, einen Konstruktor ohne Argumente in einer Klasse definiert, die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` für Makros verwendet, rufen Sie eine "keine" verfügbaren Compilerwarnung des Standardkonstruktors in der Zeile ab, in der das `IMPLEMENT_SERIAL`\-Makro verwendet wird.  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Verwenden des IMPLEMENT\_SERIAL\-Makros in der Implementierungsdatei  
 Das Makro `IMPLEMENT_SERIAL` wird verwendet, um die verschiedenen erforderlichen Funktionen zu definieren, wenn eine serialisierbare Klasse von `CObject` ableiten.  Sie verwenden dieses Makro in der Implementierungsdatei \(.CPP\) für die Klasse.  Die ersten beiden Argumente in Makro sind der Name der Klasse und den Namen seiner unmittelbaren Basisklasse.  
  
 Das dritte Argument zu diesem Makro ist ein Schemazahl.  Die Schemazahl ist im Wesentlichen eine Versionsnummer für Objekte der Klasse.  Verwenden Sie eine ganze Zahl größer oder gleich 0 für die Schemazahl. \(Verwechseln Sie diese Schemazahl nicht mit Datenbankterminologie.\)  
  
 Die MFC\-Serialisierungscode\-überprüfungen die Schemazahl, wenn Objekte in den Arbeitsspeicher gelesen werden.  Wenn die Schemazahl des Objekts auf der Festplatte nicht die Schemazahl der Klasse im Arbeitsspeicher übereinstimmt, löst die Bibliothek `CArchiveException` aus und verhindert das Programm am Lesen einer falschen Version des Objekts.  
  
 Wenn Sie Ihre `Serialize`\-Memberfunktion in der Lage sein sollen, mehrere Versionen zu lesen \- d. h, Dateien geschrieben in unterschiedlichen Versionen der Anwendung \- Sie können den Wert **VERSIONABLE\_SCHEMA** als Argument für das Makro `IMPLEMENT_SERIAL` verwenden.  So Verwendungsinformation und ein Beispiel finden Sie die `GetObjectSchema`\-Memberfunktion der Klasse `CArchive`.  
  
 Das folgende Beispiel zeigt, wie `IMPLEMENT_SERIAL` für eine Klasse, `CPerson` verwendet, die von `CObject` abgeleitet wurde:  
  
 [!CODE [NVC_MFCSerialization#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#4)]  
  
 Sobald eine serialisierbare Klasse haben, können Sie Objekte der Klasse serialisiert, wie im Artikel [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md) erläutert.  
  
## Siehe auch  
 [Serialisierung](../mfc/serialization-in-mfc.md)