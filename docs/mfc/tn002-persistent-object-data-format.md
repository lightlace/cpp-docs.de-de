---
title: 'TN002: Persistentes Objektdatenformat | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca6a78f19b43ded59efb56b87f9fe3f44887a31a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Persistentes Objektdatenformat
In diesem Hinweis werden die MFC-Routinen, die persistente C++-Objekte und das Format der Daten des Objekts unterstützen, wenn es in einer Datei gespeichert wird. Dies gilt nur für Klassen mit den [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) Makros.  
  
## <a name="the-problem"></a>Das Problem  
 Die MFC-Implementierung für persistente Daten speichert Daten für zahlreiche Objekte in einem einzelnen zusammenhängenden Teil der Datei. Des Objekts `Serialize` Methode übersetzt die Daten des Objekts in ein kompaktes binäres Format.  
  
 Die Implementierung wird sichergestellt, dass alle Daten im selben Format gespeichert, mit der [CArchive-Klasse](../mfc/reference/carchive-class.md). Er verwendet ein `CArchive` Objekt als Konvertierungsprogramm. Dieses Objekt bleibt bestehen, vom Zeitpunkt Erstellung bis zum Aufruf von [CArchive::Close](../mfc/reference/carchive-class.md#close). Diese Methode kann aufgerufen werden vom Programmierer explizit oder implizit durch den Destruktor, wenn das Programm der Bereich beendet wird, die enthält die `CArchive`.  
  
 Dieser Hinweis beschreibt die Implementierung der `CArchive` Elemente [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) und [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject). Finden Sie den Code für diese Funktionen in Arcobj.cpp und die main-Implementierung für `CArchive` in Arccore.cpp. Benutzercode rufen nicht `ReadObject` und `WriteObject` direkt. Stattdessen werden diese Objekte durch klassenspezifische als typsicherer Einfügung und Extraktion Operatoren, die automatisch vom generiert werden verwendet die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros. Der folgende code zeigt, wie `WriteObject` und `ReadObject` implizit aufgerufen werden:  
  
```  
class CMyObject : public CObject  
{  
    DECLARE_SERIAL(CMyObject) 
};  
 
IMPLEMENT_SERIAL(CMyObj, CObject, 1)  
 
// example usage (ar is a CArchive&)  
CMyObject* pObj;  
CArchive& ar;  
ar <<pObj;        // calls ar.WriteObject(pObj)  
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))  
```  
  
## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Speichern von Objekten in den Speicher (CArchive::WriteObject)  
 Die Methode `CArchive::WriteObject` schreibt Headerdaten ab, das das Objekt zu rekonstruieren. Diese Daten besteht aus zwei Teilen: der Typ des Objekts und den Status des Objekts. Diese Methode ist auch zuständig für die Verwaltung der Identität des Objekts wird geschrieben, damit nur eine einzige Kopie gespeichert wird, unabhängig von der Anzahl von Zeigern auf dieses Objekt (einschließlich zirkuläre Zeiger).  
  
 (Einfügen) speichern und Wiederherstellen von Objekten (Extrahieren) basiert auf mehrere "Manifestkonstanten." Hierbei handelt es sich um Werte, die im Binärformat gespeichert sind, und liefern Ihnen wichtige Informationen in das Archiv (Beachten Sie, dass das Präfix "w" 16-Bit-Mengen angibt):  
  
|Tag|Beschreibung|  
|---------|-----------------|  
|wNullTag|Für das Objekt NULL-Zeiger (0) verwendet.|  
|wNewClassTag|Gibt an, dass der folgende Beschreibung der Klasse noch nicht mit diesem Archivkontext (-1) ist.|  
|wOldClassTag|Gibt an, dass die Klasse des Objekts gelesenen in diesem Kontext (0 x 8000) verarbeitet wurde.|  
  
 Wenn Sie Objekte zu speichern, das Archiv verwaltet eine [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) (die `m_pStoreMap`) ist eine Zuordnung von ein gespeichertes Objekt zu einem permanenten 32-Bit-ID (PID). Eine PID wird zugewiesen, jede eindeutiges Objekt und jede eindeutige Klassennamen dar, der im Kontext des Archivs gespeichert wird. Diese PIDs ausgegeben werden sequenziell beginnend mit 1. Diese PIDs haben keine Bedeutung außerhalb des Bereichs des Archivs, und gibt insbesondere nicht zu verwechseln mit Datensatz Zahlen oder andere Elemente der Identität.  
  
 In der `CArchive` Klasse, PIDs sind 32-Bit-Version, aber sie geschrieben werden als 16-Bit-es sei denn, sie größer als 0x7FFE sind. Große PIDs werden als 0x7FFF gefolgt von der 32-Bit-PID geschrieben. Damit wird die Kompatibilität mit Projekten, die in früheren Versionen erstellt wurden.  
  
 Wird eine Anforderung gestellt wird, um ein Objekt in ein Archiv zu speichern, (in der Regel mithilfe des globalen Einfügeoperators), erfolgt eine Prüfung für ein NULL-Wert [CObject](../mfc/reference/cobject-class.md) Zeiger. Wenn der Zeiger NULL ist, ist die `wNullTag` berichtsarchiv-Datenstrom eingefügt wird.  
  
 Wenn der Zeiger nicht NULL ist und serialisiert werden kann (die Klasse ist eine `DECLARE_SERIAL` Klasse), im Code wird überprüft die `m_pStoreMap` um festzustellen, ob das Objekt wurde bereits gespeichert. Falls Ja, fügt der Code die 32-Bit-PID, die diesem Objekt zugeordnete, in der berichtsarchiv-Datenstrom.  
  
 Wenn das Objekt noch nicht gespeichert wurde, es gibt zwei Möglichkeiten zum berücksichtigen: das Objekt und der genaue Typ (d. h.-Klasse) des Objekts sind neu in diesem Archivkontext oder das Objekt weist einen genauen Typ bereits angezeigt. Um zu bestimmen, ob der Typ angezeigt wurde, Code Abfragen der `m_pStoreMap` für eine [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) -Objekt, entspricht die `CRuntimeClass` Objekt zugewiesen ist, mit dem Objekt gespeichert wird. Wenn eine Übereinstimmung besteht, `WriteObject` Fügt ein Tag, das die bitweise `OR` von `wOldClassTag` und diesen Index. Wenn die `CRuntimeClass` ist neu in diesem Archivkontext `WriteObject` weist eine neue PID für diese Klasse und fügt es in das Archiv, vorangestellt der `wNewClassTag` Wert.  
  
 Der Deskriptor für diese Klasse wird dann in das Archiv mit eingefügt die `CRuntimeClass::Store` Methode. `CRuntimeClass::Store`die Anzahl von Schema für die Klasse (siehe unten) und der ASCII-Text-Name der Klasse eingefügt. Beachten Sie, dass die Verwendung von ASCII-Text-Name die Eindeutigkeit des Archivs anwendungsübergreifend nicht garantiert. Aus diesem Grund sollten Sie die Datendateien Wiederherstellungpunkte mit beschädigten markieren. Nach der Einfügung die Klasseninformationen versetzt das Archiv das Objekt in der `m_pStoreMap` und ruft dann die `Serialize` Methode zum Einfügen von Klasse-spezifische Daten. Platzieren das Objekt in der `m_pStoreMap` vor dem Aufruf `Serialize` verhindert, dass mehrere Kopien des Objekts im Speicher gespeichert.  
  
 Bei der Rückgabe an den ursprünglichen Aufrufer (in der Regel vom Stamm des Netzwerks von Objekten), müssen Sie aufrufen [CArchive::Close](../mfc/reference/carchive-class.md#close). Wenn Sie beabsichtigen, andere [CFile](../mfc/reference/cfile-class.md)Vorgänge, die Sie aufrufen müssen die `CArchive` Methode [leeren](../mfc/reference/carchive-class.md#flush) auf eine Beschädigung des Archivs verhindert werden.  
  
> [!NOTE]
>  Diese Implementierung erzwingt einen festen Grenzwert von 0x3FFFFFFE Indizes pro Archivkontext. Diese Zahl stellt die maximale Anzahl von eindeutigen Objekte und Klassen, die in einem einzigen Archiv gespeichert werden können, aber eine einzelne Datei kann eine unbegrenzte Anzahl von Kontexten Archiv haben.  
  
## <a name="loading-objects-from-the-store-carchivereadobject"></a>Laden von Objekten aus dem Store (CArchive::ReadObject)  
 Laden (Extrahieren)-Objekten verwendet die `CArchive::ReadObject` Methode und die Umkehrung von `WriteObject`. Wie bei `WriteObject`, `ReadObject` heißt nicht direkt von Benutzercode; Benutzercode sollte Operators als typsicherer Extraktion ruft Aufrufen `ReadObject` mit dem erwarteten `CRuntimeClass`. Dadurch wird die Integrität Typ des Extrahierungsvorgangs sichergestellt.  
  
 Da die `WriteObject` Implementierung zugewiesen zunehmenden PIDs, beginnend mit 1 (0 ist vordefiniert, wie das NULL-Objekt), die `ReadObject` Implementierung kann ein Array verwenden, um den Status des Kontexts Archiv zu verwalten. Beim ist eine PID aus dem Speicher lesen, ist die PID größer als die aktuelle Obergrenze für die `m_pLoadArray`, `ReadObject` weiß, dass ein neues Objekt (oder die Beschreibung der Klasse) folgt.  
  
## <a name="schema-numbers"></a>Schema-Zahlen  
 Der Schema-Anzahl, die die Klasse zugewiesen wird bei der `IMPLEMENT_SERIAL` -Methode der Klasse festgestellt wird, ist die "Version" der Implementierung der Klasse. Das Schema für die Implementierung der Klasse verweist, nicht auf die Anzahl der Aufrufe ein angegebenes Objekt wurde persistent (in der Regel die Objektversion genannt).  
  
 Wenn Sie beabsichtigen, mehrere verschiedene Implementierungen von derselben Klasse im Zeitverlauf, erhöht das Schema, wie Sie Ihr Objekts überarbeiten `Serialize` methodenimplementierung können Sie Code schreiben, die mit älteren Versionen von gespeicherten Objekte laden kann die Implementierung.  
  
 Die `CArchive::ReadObject` Methode löst eine [CArchiveException](../mfc/reference/carchiveexception-class.md) Wenn diverse Schema in den permanenten Speicher, die die Anzahl von Schema für die Beschreibung der Klasse im Speicher nicht gefunden wird. Es ist nicht einfach zu dieser Ausnahme zu beheben.  
  
 Sie können `VERSIONABLE_SCHEMA` zusammen mit (bitweise `OR`) Ihrer Version des Datenbankschemas, behalten Sie diese Ausnahme ausgelöst wird. Mit `VERSIONABLE_SCHEMA`, kann Ihr Code die entsprechende Maßnahme einleiten, dessen `Serialize` Funktion durch Überprüfen des Rückgabewerts aus [CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema).  
  
## <a name="calling-serialize-directly"></a>Aufrufen direkt serialisieren.  
 In vielen Fällen ist den Aufwand für das allgemeine Objekt Archiv Schema `WriteObject` und `ReadObject` ist nicht erforderlich. Dies ist zum Serialisieren der Daten in den meisten Fällen eine [CDocument](../mfc/reference/cdocument-class.md). In diesem Fall die `Serialize` Methode der `CDocument` direkt, nicht mit den extrahieren oder Insert-Operator aufgerufen wird. Der Inhalt des Dokuments können wiederum die allgemeinere Objekt-Archiv-Schema verwenden.  
  
 Aufrufen von `Serialize` direkt hat die folgenden vor- und Nachteile:  
  
-   Keine zusätzlichen Bytes werden hinzugefügt, in das Archiv, bevor oder nachdem das Objekt serialisiert wird. Dies nicht nur durch die die gespeicherten Daten kleiner, sondern ermöglicht Ihnen implementieren `Serialize` Dateiformate für Routinen, die jede verarbeiten können.  
  
-   Die MFC-Bibliothek optimiert ist daher die `WriteObject` und `ReadObject` Implementierungen und verwandte Auflistungen werden nicht verknüpft werden in die Anwendung, wenn Sie das Schema der allgemeinere Objekt Archiv für einige andere Zwecke benötigen.  
  
-   Ihr Code verfügt nicht über die Wiederherstellung des alten Schema Zahlen. Dadurch wird Ihr Dokument Serialisierungscode verantwortlich für die Codierung Schema Zahlen, Format Versionsnummern oder beliebige identifizieren Sie Zahlen am Anfang von Datendateien verwenden.  
  
-   Jedes Objekt, das durch einen direkten Aufruf serialisiert wird `Serialize` dürfen keine verwenden `CArchive::GetObjectSchema` oder müssen Handle der Rückgabewert ("uint")-1 gibt an, dass die Version nicht kennt.  
  
 Da `Serialize` wird aufgerufen, direkt auf das Dokument kann nicht in der Regel für die untergeordneten Objekte des Dokuments, das Verweise auf deren übergeordnetes Dokument zu archivieren. Diese Objekte müssen erhalten einen Zeiger auf ihre Containerdokument explizit, oder verwenden Sie [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) Funktion zum Zuordnen der `CDocument` Zeiger auf eine PID, bevor diese Back Zeiger archiviert werden.  
  
 Wie bereits erwähnt, sollten Sie die Version zu codieren und Klasse Informationen selbst bei Aufruf `Serialize` direkt, aktivieren Sie das Format später ändern, während Sie gleichzeitig Abwärtskompatibilität mit älteren Dateien. Die `CArchive::SerializeClass` Funktion kann explizit aufgerufen werden, bevor Sie direkt Serialisieren eines Objekts oder eine Basisklasse aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

