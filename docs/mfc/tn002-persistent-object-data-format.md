---
title: 'TN002: Persistentes Objektdatenformat'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: 6d64799dc17b4b3ddc5c455333b10282e4748b09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306193"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Persistentes Objektdatenformat

In diesem Hinweis wird beschrieben, die MFC-Routinen, die persistente C++-Objekte und das Format der Daten des Objekts zu unterstützen, wenn es in einer Datei gespeichert wird. Dies gilt nur für Klassen mit dem [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) Makros.

## <a name="the-problem"></a>Das Problem

Die MFC-Implementierung für persistente Daten speichert Daten für viele Objekte in einem einzelnen zusammenhängenden Teil einer Datei. Des Objekts `Serialize` -Methode übersetzt die Daten des Objekts in ein kompaktes binäres Format.

Die Implementierung wird sichergestellt, dass alle Daten werden im selben Format gespeichert, mit der [CArchive-Klasse](../mfc/reference/carchive-class.md). Er verwendet eine `CArchive` Objekt als Übersetzer. Dieses Objekt beibehalten wird, ab dem Zeitpunkt der Erstellung wird erst nach dem Aufruf [CArchive::Close](../mfc/reference/carchive-class.md#close). Diese Methode kann aufgerufen werden entweder durch den Programmierer explizit oder implizit durch den Destruktor beim Beenden des Programms über des Bereichs, der enthält die `CArchive`.

Dieser Hinweis beschreibt die Implementierung der `CArchive` Mitglieder [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) und [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject). Sehen Sie den Code für diese Funktionen in Arcobj.cpp und die main-Implementierung für `CArchive` in Arccore.cpp. Benutzercode wird nicht aufgerufen. `ReadObject` und `WriteObject` direkt. Stattdessen werden diese Objekte durch mandantenklassen geltenden schemaanpassungen typsichere Einfügung und Extraktion Operatoren verwendet, die durch die Makros DECLARE_SERIAL und IMPLEMENT_SERIAL automatisch generiert werden. Der folgende code zeigt, wie `WriteObject` und `ReadObject` werden implizit aufgerufen:

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

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Speichern von Objekten in den Store (CArchive::WriteObject)

Die Methode `CArchive::WriteObject` schreibt die Daten im Anforderungsheader, die verwendet wird, um das Objekt zu rekonstruieren. Diese Daten besteht aus zwei Teilen: der Typ des Objekts und den Zustand des Objekts. Diese Methode ist auch zuständig für die Verwaltung von der Identität des Objekts geschrieben wird, sodass nur eine einzige Kopie gespeichert werden, unabhängig von der Anzahl von Zeigern auf dieses Objekt (einschließlich zirkuläre Zeiger).

Speichern (Einfügen) und Wiederherstellen von (Extrahieren)-Objekten basiert auf mehrere "Manifestkonstanten." Dies sind die Werte, die im Binärformat gespeichert werden und bieten wichtige Informationen in das Archiv (Beachten Sie, dass das Präfix "w" 16-Bit-Mengen angibt):

|Tag|Beschreibung|
|---------|-----------------|
|wNullTag|Für das Objekt NULL-Zeiger (0) verwendet.|
|wNewClassTag|Gibt an, dass die folgende Beschreibung der Klasse noch nicht mit diesem Archivkontext (-1) ist.|
|wOldClassTag|Gibt an, dass die Klasse des Objekts gelesen wird in diesem Kontext (0 x 8000) vorgekommen ist.|

Wenn Sie Objekte zu speichern, das Archiv verwaltet eine [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) (die *M_pStoreMap*) Dies ist eine Zuordnung ein gespeichertes Objekt zu einem permanenten 32-Bit-ID (PID). Eine PID erhält jedes eindeutige Objekt und jede eindeutige Klassennamen, die im Kontext des Archivs gespeichert wird. Diese PIDs werden, sequenziell beginnend mit 1 übergeben. Diese PIDs haben keine Bedeutung außerhalb des Bereichs des Archivs und sind vor allem nicht zu verwechseln mit Datensatznummern oder andere Elemente der Identität.

In der `CArchive` -Klasse, PIDs werden 32-Bit, aber werden geschrieben als 16-Bit, außer sie sind größer als 0x7FFE. Große PIDs werden als 0x7FFF gefolgt von der 32-Bit-PID geschrieben. Hierdurch bleibt die Kompatibilität mit Projekten, die in früheren Versionen erstellt wurden.

Wenn eine Anforderung gesendet wird, um ein Objekt in ein Archiv (in der Regel mithilfe der globalen einfügungsoperator) zu speichern, wird überprüft, NULL [CObject](../mfc/reference/cobject-class.md) Zeiger. Wenn der Zeiger NULL ist, ist die *wNullTag* berichtsarchiv-Datenstrom eingefügt wird.

Wenn der Zeiger nicht NULL ist und serialisiert werden kann (die Klasse ist eine `DECLARE_SERIAL` Klasse), dem Code wird überprüft die *M_pStoreMap* um festzustellen, ob das Objekt wurde bereits gespeichert. Falls Ja, fügt den Code in den Stream Archiv mit dem Objekt verknüpfte 32-Bit-PID.

Wenn das Objekt noch nicht gespeichert wurde, es gibt zwei Möglichkeiten zu berücksichtigen: das Objekt und den genauen Typ (d. h.-Klasse) des Objekts sind neu in diesem Archivkontext oder das Objekt weist ein genauer Typ bereits gesehen. Um festzustellen, ob der Typ einmal verwendet wurde, Code Abfragen die *M_pStoreMap* für eine [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) -Objekt, das entspricht der `CRuntimeClass` Objekt verknüpft ist, mit dem Objekt gespeichert wird. Wenn eine Übereinstimmung vorliegt, `WriteObject` Fügt ein Tag, das die bitweise `OR` von *wOldClassTag* und diesen Index. Wenn die `CRuntimeClass` ist neu in diesem Archivkontext `WriteObject` Klasse eine neue PID zugewiesen, und fügt es in das Archiv, vorangestellt wird die *wNewClassTag* Wert.

Der Deskriptor für diese Klasse wird dann in das Archiv mit eingefügt der `CRuntimeClass::Store` Methode. `CRuntimeClass::Store` die Anzahl von Schema für die Klasse (siehe unten) und den Namen des ASCII-Text der Klasse eingefügt. Beachten Sie, dass die Verwendung mit dem Namen der ASCII-Text die Eindeutigkeit des Archivs in Anwendungen nicht garantiert. Aus diesem Grund sollten Sie die Datendateien, um zu verhindern, dass eine Beschädigung markieren. Nach der Einfügung von die Klasseninformationen das Archiv, erhält das Objekt in der *M_pStoreMap* und ruft dann die `Serialize` Methode zum Einfügen von Klasse-spezifischen Daten. Platzieren das Objekt in der *M_pStoreMap* vor dem Aufruf `Serialize` verhindert, dass mehrere Kopien des Objekts im Speicher gespeichert wird.

Bei der Rückgabe an den ursprünglichen Aufrufer (in der Regel der Stamm des Netzwerks von Objekten), müssen Sie aufrufen [CArchive::Close](../mfc/reference/carchive-class.md#close). Wenn Sie beabsichtigen, andere [CFile](../mfc/reference/cfile-class.md)Vorgänge, die Sie aufrufen müssen die `CArchive` Methode [leeren](../mfc/reference/carchive-class.md#flush) um eine Beschädigung des Archivs zu verhindern.

> [!NOTE]
>  Diese Implementierung setzt eine harte Grenze von 0x3FFFFFFE Indizes pro Archivkontext. Diese Zahl steht für die maximale Anzahl von eindeutigen Objekten und Klassen, die in einem einzelnen Archiv gespeichert werden können, aber die Datei auf einem einzelnen Datenträger kann eine unbegrenzte Anzahl von Kontexten, Archiv haben.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>Laden von Objekten aus dem Store (CArchive::ReadObject)

Laden von (Extrahieren)-Objekten verwendet die `CArchive::ReadObject` Methode ist die Umkehrung von `WriteObject`. Wie bei `WriteObject`, `ReadObject` wird nicht aufgerufen, direkt von Benutzercode; Benutzercode sollte die typsichere Extraktionsoperator, die Aufrufe aufrufen `ReadObject` mit den erwarteten `CRuntimeClass`. Dadurch wird sichergestellt, die Integrität der Typ des Extrahierungsvorgangs.

Da die `WriteObject` Implementierung zugewiesen zunehmende PIDs, beginnend mit 1 (0 ist vordefiniert, wie das NULL-Objekt), die `ReadObject` Implementierung kann ein Array verwenden, um den Status des Kontexts Archive beizubehalten. Beim ist eine PID aus dem Speicher lesen, ist die PID größer als die aktuelle obere Grenze der *M_pLoadArray*, `ReadObject` weiß, dass ein neues Objekt (oder die Beschreibung der Klasse) folgt.

## <a name="schema-numbers"></a>Schema-Zahlen

Der Schema-Anzahl, die die Klasse zugewiesen wird bei der `IMPLEMENT_SERIAL` -Methode der Klasse festgestellt wird, ist die "Version" an, der die Implementierung der Klasse. Das Schema für die Implementierung der Klasse verweist, nicht auf die Anzahl der Aufrufe ein angegebenes Objekt wurde als persistente (in der Regel die Objektversion genannt).

Wenn Sie beabsichtigen, mehrere verschiedene Implementierungen der gleichen Klasse im Laufe der Zeit zu warten, erhöht das Schema, wie Sie des Objekts überarbeiten `Serialize` methodenimplementierung ermöglicht Ihnen, Code zu schreiben, die mit älteren Versionen von gespeicherten Objekte laden kann die Implementierung.

Die `CArchive::ReadObject` Methode löst eine [CArchiveException](../mfc/reference/carchiveexception-class.md) Wenn trifft es zahlreiche Schema in den permanenten Speicher, der die Anzahl von Schema für die Beschreibung der Klasse im Speicher unterscheidet. Es ist nicht einfach, diese Ausnahme beheben.

Können Sie `VERSIONABLE_SCHEMA` in Kombination mit (bitweise **oder**) die Schemaversion, zu diese Ausnahme ausgelöst wird. Mithilfe von `VERSIONABLE_SCHEMA`, Ihren Code kann die entsprechende Aktion ausführen, dessen `Serialize` Funktion durch Überprüfen des Rückgabewerts aus [CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema).

## <a name="calling-serialize-directly"></a>Aufruf direkt serialisieren.

In vielen Fällen den Aufwand für das allgemeine Objekt Archiv-Schema der `WriteObject` und `ReadObject` ist nicht erforderlich. Dies ist der allgemeine Fall Serialisieren der Daten in einem [CDocument](../mfc/reference/cdocument-class.md). In diesem Fall die `Serialize` Methode der `CDocument` wird nicht mit den Operatoren extrahieren oder Insert direkt aufgerufen. Der Inhalt des Dokuments können wiederum das allgemeine Objekt Archiv-Schema verwenden.

Aufrufen von `Serialize` direkt hat die folgenden vor- und Nachteile:

- Keine zusätzlichen Bytes werden hinzugefügt, in das Archiv vor oder nach dem das Objekt serialisiert wird. Dies nicht nur durch die die gespeicherten Daten kleiner, jedoch können Sie implementieren `Serialize` Dateiformate für Routinen, die jede verarbeiten können.

- Die MFC-Bibliothek wird optimiert. daher `WriteObject` und `ReadObject` Implementierungen und verwandte Auflistungen nicht verknüpft werden in Ihre Anwendung, wenn Sie das allgemeine Objekt Archiv-Schema zu einem anderen Zweck benötigen.

- Ihr Code muss nicht aus dem alten Schema Zahlen wiederherstellen. Dadurch wird Ihr Dokument Serialisierung-Code für die Codierung Schema Zahlen, Format-Versionsnummern oder beliebige identifizieren Sie Zahlen verantwortlich am Anfang der Datendateien verwenden.

- Jedes Objekt, das mit einem direkten Aufruf serialisiert wird `Serialize` dürfen keine verwenden `CArchive::GetObjectSchema` oder müssen Handle der Rückgabewert (UINT) – 1 gibt an, dass die Version unbekannt war.

Da `Serialize` wird aufgerufen, direkt in Ihrem Dokument kann nicht in der Regel für die untergeordneten Objekte des Dokuments, das Verweise auf ihr übergeordnetes Dokument zu archivieren. Diese Objekte müssen mit einem Zeiger versehen ihre Container-Dokument explizit, oder verwenden Sie [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) Funktion zum Zuordnen der `CDocument` Zeiger auf eine PID, bevor diese Back Zeiger archiviert werden.

Wie bereits erwähnt, sollten Sie die Version zu codieren und über die Klasse selbst beim Aufruf von `Serialize` direkt, sodass Sie das Format später ändern, während gleichzeitig Abwärtskompatibilität mit älteren Dateien. Die `CArchive::SerializeClass` Funktion kann explizit aufgerufen werden, bevor Sie direkt Serialisieren eines Objekts oder eine Basisklasse aufrufen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
