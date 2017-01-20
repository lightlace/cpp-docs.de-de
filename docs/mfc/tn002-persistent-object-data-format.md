---
title: "TN002: Persistentes Objektdatenformat"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive-Klasse, Unterstützung für persistente Daten"
  - "Persistente C++-Objekte"
  - "Persistente Objektdaten"
  - "TN002"
  - "VERSIONABLE_SCHEMA-Makro"
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
caps.latest.revision: 22
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# TN002: Persistentes Objektdatenformat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die MFC\-Routinen, die permanente C\+\+\-Objekte und der Stil der Objektdaten unterstützen, wenn sie in einer Datei gespeichert wird.  Dies gilt nur für Klassen mit [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) und [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) zu Makros.  
  
## Das Problem  
 Die MFC\-Implementierung for Persistent Datenspeicherdaten für viele Objekte in einem zusammenhängenden Teil einer Datei.  Die `Serialize`\-Methode des Objekts verschoben die Daten des Objekts in ein komprimiertes Binärformat.  
  
 Die Implementierung wird sichergestellt, dass alle Daten im gleichen Format gespeichert werden, indem Sie [CArchive Class](../mfc/reference/carchive-class.md) verwenden.  Sie verwendet ein `CArchive`\-Objekt als Übersetzer.  Dieses Objekt besteht der Zeit erhalten, die es erstellt wird, wenn Sie [CArchive::Close](../Topic/CArchive::Close.md) aufrufen.  Diese Methode kann entweder durch den Programmierer oder implizit durch den Destruktor explizit aufgerufen werden beim Beenden des Programms der Bereich, der `CArchive` enthält.  
  
 Dieser Hinweis beschreibt die Implementierung der `CArchive`\-Member [CArchive::ReadObject](../Topic/CArchive::ReadObject.md) und [CArchive::WriteObject](../Topic/CArchive::WriteObject.md).  Sie suchen den Code für diese Funktionen in Arcobj.cpp und die Hauptimplementierung für `CArchive` in Arccore.cpp.  Benutzercode ruft nicht `ReadObject` und `WriteObject` direkt auf.  Stattdessen werden diese Objekte durch klassenspezifischen typsicheren Einfügungs\- und Extraktionsoperatoren verwendet, die automatisch durch die Makros `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` generiert werden.  Der folgende Code zeigt, wie `WriteObject` und `ReadObject` implizit aufgerufen werden:  
  
```  
class CMyObject : public CObject  
{  
    DECLARE_SERIAL(CMyObject)  
};  
  
IMPLEMENT_SERIAL(CMyObj, CObject, 1)  
  
// example usage (ar is a CArchive&)  
CMyObject* pObj;  
CArchive& ar;  
ar << pObj;        // calls ar.WriteObject(pObj)  
ar >> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))  
```  
  
## Einsparungs\-Objekte den Speicher \(CArchive::WriteObject\)  
 Die Methode `CArchive::WriteObject` schreibt Kopfzeilendaten, die verwendet wird, um das Objekt zu rekonstruieren.  Diese Daten bestehen aus zwei Teilen: der Typ des Objekts und der Zustand des Objekts.  Außerdem ist diese Methode für die Beibehaltung der Identität des Objekts zuständig, die geschrieben, dass nur eine einzige Kopie gespeichert wird, unabhängig von der Anzahl von Zeigern zu diesem Objekt \(z zirkuläre Zeiger\).  
  
 Das Speichern \(Einfügen\) und Wiederherstellen \(Extrahieren\) von Objekten beruht auf einigen "Manifestkonstanten." Diese sind Werte, die in der Binärdatei gespeichert und wichtige Informationen dem Archiv bereitstellen werden \(beachten Sie das "w\-" Präfix angibt 16\-Bit\-Mengen\):  
  
|Tag|**Beschreibung**|  
|---------|----------------------|  
|wNullTag|Wird für UNGÜLTIGE Objektzeiger \(0\).|  
|wNewClassTag|Gibt Klassenbeschreibung an, die neu ist zu diesem Archivkontext folgt \(\- 1\).|  
|wOldClassTag|Gibt Klasse des Objekts an, das angezeigt wird gelesen, ist in diesem Kontext \(0x8000\).|  
  
 Wenn es Objekten speichert, wartet das Archiv [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) \( `m_pStoreMap`\) das eine Zuordnung von einem gespeicherten Objekt zu einem dauerhaften 32\-Bit\-Bezeichner \(PID\) ist.  Ein PID wird auf jedes eindeutigen Objekt und auf die eindeutige Klassennamen zugewiesen, der im Rahmen des Archivs gespeichert wird.  Dies ist ausgeteiltes PID sequenziell beginnen mit 1.  Dies PID hat keinen Schritt außerhalb des Projektumfangs des Archivs und soll insbesondere nicht mit Datensatznummern oder anderen Identitätselementen verwechselt werden.  
  
 In der `CArchive`\-Klasse ist PID 32\-Bit, ist jedoch als 16\-Bit\- ausgeschrieben, es sei denn, sie größer als 0x7FFE sind.  Großes PID wird als 0x7FFF geschrieben, das vom 32\-Bit\-Prozess PID folgt.  Hierdurch bleibt Kompatibilität mit Projekten verwaltet, die in früheren Versionen erstellt wurden.  
  
 Wenn eine Anforderung, ein Objekt zu einem Archiv zu speichern \(normalerweise mit dem globalen Einfügungsoperators\) gemacht wird, wird eine Überprüfung einen Zeiger NULL [CObject](../mfc/reference/cobject-class.md) durchgeführt.  Wenn der Zeiger NULL ist, wird `wNullTag` in den Archivstream eingefügt.  
  
 Wenn der Mauszeiger nicht NULL ist und serialisiert werden kann \(die Klasse wird eine `DECLARE_SERIAL`\-Klasse\), die Code überprüft `m_pStoreMap`, zu überprüfen, ob das Objekt bereits gespeicherten Kommunikation.  Wenn es besitzt, fügt der Code die 32\-Bit\-Version ein PID, das diesem Objekt in den Archivstream zugeordnet ist.  
  
 Wenn das Objekt nicht zuvor gespeichert wurde, gibt es zwei Möglichkeiten, zu beachten: entweder sind das Objekt und der genaue Typ \(d, Klasse\) des Objekts zu diesem Archivkontext neu, oder das Objekt von einem genauen bereits gesehenen Typ.  Um festzustellen ob Typ betrachtet wurde, fragt der Code `m_pStoreMap` für ein Objekt die mit [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) ab, die das `CRuntimeClass`\-Objekt mit dem Objekt zugeordnet ist, die gespeichert wurde.  Wenn eine Übereinstimmung, wird `WriteObject` ein Tag ein, den bitweisen `OR` von `wOldClassTag` und von diesem Index ist.  Wenn `CRuntimeClass` zu diesem Archivkontext neu ist, weist `WriteObject` dieser Klasse ein neues PID zu und fügt sie in das Archiv ein voraus, vom Wert `wNewClassTag`.  
  
 Der ein für diese Klasse wird in das Archiv mithilfe der `CRuntimeClass::Store`\-Methode eingefügt.  `CRuntimeClass::Store` fügt die Schemazahl der Klasse \(siehe unten\) und das entsprechende ASCII\- unterstützt Namen der Klasse.  Beachten Sie, dass der Verwendung des ASCII\-Textnamen nicht Eindeutigkeit des Archivs über Anwendungen gewährleistet.  Deshalb sollten Sie die Datendateien kennzeichnen, um Beschädigungen zu vermeiden.  Nach dem Einfügen der Klasseninformationen, aktiviert das Archiv das Objekt in `m_pStoreMap` und ruft dann die `Serialize`\-Methode auf, um eine klassenspezifische Daten einzufügen.  Das Platzieren des Objekts in `m_pStoreMap` vor, Aufrufen von `Serialize` verhindert, mehrere Kopien des Objekts angegeben gespeichert werden den Speicher.  
  
 Bei Rückgabe an den ursprünglichen Aufrufer \(normalerweise der Stamm vom Netzwerk von Objekten\), müssen Sie [CArchive::Close](../Topic/CArchive::Close.md) aufrufen.  Wenn Sie planen, [Die C\-Datei](../mfc/reference/cfile-class.md) andere Vorgänge auszuführen, müssen Sie die `CArchive`[Leeren](../Topic/CArchive::Flush.md) aufrufen, um Beschädigung des Archivs zu verhindern.  
  
> [!NOTE]
>  Diese Implementierung wird eingeschränkt einen festen Grenzwert von Indizes 0x3FFFFFFE pro Archivkontext auf.  Diese Zahl stellt die maximale Anzahl eindeutiger Objekte und Klassen dar, die in einem einzelnen " gespeichert werden können, ohne einzelne Datenträgerdatei kann eine unendliche Anzahl von Archivkontexten haben.  
  
## Laden\-Objekte vom Speicher \(CArchive::ReadObject\)  
 Das Laden \(Extrahieren\) \- Verwendung die `CArchive::ReadObject`\-Methode auf und ist das Gegenteil von `WriteObject`.  Wie bei `WriteObject`, wird `ReadObject` nicht direkt durch Benutzercode aufgerufen; Benutzercode sollte den typsicheren Extraktionsoperator aufrufen, der mit `ReadObject` erwarteten `CRuntimeClass` aufruft.  Dies stellt sicher die Typintegrität des Auszugvorgangs.  
  
 Da die `WriteObject` Implementierung zunehmendes PID zugewiesener, beginnend mit 1 \(0 wird z das UNGÜLTIGE Objekt vordefiniert\), kann die Implementierung `ReadObject` ein Array verwenden, um den Zustand des Archivkontexts beizubehalten.  Wenn ein PID aus dem Speicher gelesen wird, wenn das PID höher als die aktuelle Obergrenze `m_pLoadArray` ist, weiß `ReadObject`, dass ein neues Objekt \(oder Klassenbeschreibung\) folgt.  
  
## Schema\-Zahlen  
 Die Schemazahl der Klasse, die zugewiesen wird, wenn die `IMPLEMENT_SERIAL`\-Methode der Klasse vorkommt, ist die "Version" Klassenimplementierung.  Das Schema steht die Implementierung der Klasse, nicht der Häufigkeit an, die ein angegebenes Objekt erhalten gemacht wurde \(normalerweise wird als die Objektversion\).  
  
 Wenn Sie beabsichtigen, mehrere verschiedene Implementierungen der gleichen Klasse im Zeitverlauf beizubehalten, aktiviert das Erhöhen des Schemas, während Sie `Serialize`\-Methodenimplementierung des Objekts, überarbeiten Sie, Code zu schreiben, der die Objekte geladen werden kann, die mit früheren Versionen der Implementierung gespeichert werden, verwendet.  
  
 Die `CArchive::ReadObject`\-Methode löst [CArchiveException](../mfc/reference/carchiveexception-class.md) aus, wenn sie eine Schemazahl im permanentem Speicher trifft, der von der Schemazahl der Klassenbeschreibung im Arbeitsspeicher unterscheidet.  Sich zu erholen ist nicht leicht, dieser Ausnahme.  
  
 Sie können `VERSIONABLE_SCHEMA` verwenden, die kombiniert wird mit \(bitweise `OR`\) der Schemaversion, um diese von Ausnahme ausgelöst werden.  Durch die `VERSIONABLE_SCHEMA` verwendet, kann der Code die entsprechende Aktion in seiner `Serialize`\-Funktion durchführen, indem Sie den Rückgabewert von [CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md).  
  
## Das Aufrufen serialisieren direkt  
 In vielen Fällen ist der Verwaltungsaufwand des allgemeinen Objektarchivschemas von `WriteObject` und `ReadObject` nicht erforderlich.  Dies ist der allgemeine Fall vom Serialisieren der Daten im [CDocument](../mfc/reference/cdocument-class.md).  In diesem Fall wird die `Serialize`\-Methode `CDocument` direkt, nicht mit den Auszug\- oder Einfügungsoperatoren aufgerufen.  Der Inhalt des Dokuments verwendet möglicherweise wiederum das allgemeinere Objektarchivschema.  
  
 Das Aufrufen von `Serialize` entspricht direkt die folgenden Vorteile und Nachteile:  
  
-   Alle zusätzlichen Bytes werden dem Archiv hinzugefügt, bevor oder nachdem das Objekt serialisiert wird.  Dadurch können Sie die gespeicherten Daten kleiner, aber ermöglicht es Ihnen, `Serialize` Routinen zu implementieren, die alle diese Dateiformate behandeln können.  
  
-   Das MFC ist optimiert, sodass Implementierungen die `WriteObject` und `ReadObject` und zugehörigen Auflistungen nicht in der Anwendung verknüpft, es sei denn, Sie das allgemeinere Objektarchivschema zu einem anderen Zweck benötigen.  
  
-   Der Code muss nicht von alten Schemazahlen beheben.  Dadurch wird der Dokumentserialisierungscode zuständig für das Codieren von Schemazahlen, Dateiformatversionsnummern, bzw. den Identifizierungsnummern Sie am Anfang der Datendateien verwenden.  
  
-   Jedes Objekt, deren mit einem direkten Aufruf von `Serialize` darf `CArchive::GetObjectSchema` verwenden muss nicht oder behandeln Rückgabewert serialisiert wird \(UINT\) \- 1 angibt, dass die Version nicht bekannt war.  
  
 Da `Serialize` direkt im Dokument aufgerufen wird, ist sie normalerweise nicht für die Unterobjekte des Dokuments zu den Archivverweisen auf ihrem übergeordneten Dokument möglich.  Diese Objekte müssen einen Zeiger auf den Containerdokument explizit angegeben werden, oder Sie müssen die [CArchive::MapObject](../Topic/CArchive::MapObject.md)\-Funktion verwenden, um dem `CDocument` Zeiger zu einem PID zuzuordnen, bevor diese von Zeiger archiviert werden.  
  
 Wie bereits erwähnt, sollten Sie die Version und die Klasseninformationen Code sicher, wenn Sie `Serialize` direkt aufrufen und Sie aktivieren, um das Format später ändern der Abwärtskompatibilität mit älteren Dateien beibehalten.  Die `CArchive::SerializeClass`\-Funktion kann explizit aufgerufen werden, bevor direkt ein Objekt serialisiert oder bevor eine Basisklasse aufruft.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)