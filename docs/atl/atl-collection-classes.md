---
title: ATL-Auflistungsklassen
ms.date: 11/19/2018
helpviewer_keywords:
- DestructElements function
- collection classes, choosing
- ConstructElements function
- SerializeElements function
- traits classes
- collection classes, about collection classes
- CTraits classes
- collection classes
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
ms.openlocfilehash: 70ca283468a51b4214273698a532ce2a85d52b44
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774976"
---
# <a name="atl-collection-classes"></a>ATL-Auflistungsklassen

ATL stellt viele Klassen zum Speichern und Zugreifen auf Daten bereit. Welche Klasse Sie verwenden möchten, hängt von mehreren Faktoren ab, einschließlich:

- Die Menge der Daten gespeichert werden

- Effizienz und Leistung beim Zugriff auf die Daten

- Der Zugriff auf die Daten anhand des Indexes oder anhand des Schlüssels

- Wie werden die Daten sortiert.

- Geschmackssache

## <a name="small-collection-classes"></a>Kleine Auflistungsklassen

ATL stellt die folgenden Klassen für Arrays bereit, für den Umgang mit einer kleinen Anzahl von Objekten. Diese Klassen sind jedoch begrenzt und intern entwickelt für die Verwendung von ATL Es wird nicht empfohlen, die Sie in Ihren Programmen verwenden.

|Klasse|Typ des Datenspeichers|
|-----------|--------------------------|
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Eine Arrayklasse für den Umgang mit einer kleinen Anzahl von Objekten implementiert.|
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Eine Zuordnungsklasse für den Umgang mit einer kleinen Anzahl von Objekten implementiert.|

## <a name="general-purpose-collection-classes"></a>Allgemeiner-Auflistungsklassen

Die folgenden Klassen implementieren, Arrays, Listen und Zuordnungen und werden als allgemeine Sammlungsklassen bereitgestellt:

|Klasse|Typ des Datenspeichers|
|-----------|--------------------------|
|[CAtlArray](../atl/reference/catlarray-class.md)|Implementiert ein Array.|
|[CAtlList](../atl/reference/catllist-class.md)|Implementiert eine Liste.|
|[CAtlMap](../atl/reference/catlmap-class.md)|Implementiert eine Zuordnungsstruktur, bei dem Daten mit Schlüssel oder Wert verwiesen werden kann.|
|[CRBMap](../atl/reference/crbmap-class.md)|Implementiert eine Zuordnungsstruktur, die mit dem Rot-Schwarz-Algorithmus.|
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Implementiert eine Rot-Schwarz-Multimappingstruktur an.|

Diese Klassen werden viele Programmierfehler, bei der Verwendung in Debugbuilds abgefangen, aber zur Leistung zu erzielen, werden diese Überprüfungen nicht in Retail-Builds ausgeführt werden.

## <a name="specialized-collection-classes"></a>Spezielle Auflistungsklassen

Spezialisiertere Auflistungsklassen werden auch für die Verwaltung von Arbeitsspeicher und Benutzeroberfläche Zeigern bereitgestellt:

|Klasse|Zweck|
|-----------|-------------|
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Stellt Methoden bereit, wenn Sie ein Array von intelligenten Zeigern zu erstellen.|
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Stellt Methoden bereit, wenn Sie eine Liste von intelligenten Zeigern zu erstellen.|
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|Speichert `IUnknown` Zeiger als Parameter verwendet werden soll, und die [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.|
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Stellt Methoden bereit, beim Erstellen einer Liste von Heap-Zeigern.|
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|Stellt Methoden bereit, wenn Sie ein Array von COM-Schnittstellenzeiger zu erstellen.|
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|Stellt Methoden bereit, wenn Sie eine Liste der COM-Schnittstellenzeiger zu erstellen.|

## <a name="choosing-a-collection-class"></a>Auswahl einer Sammlungsklasse

Jede der verfügbaren Auflistungsklassen bietet unterschiedliche Leistungsmerkmale, wie in der folgenden Tabelle gezeigt.

- Spalten 2 und 3 beschrieben, jede Klasse in der Reihenfolge und Zugriff auf Eigenschaften. In der Tabelle bedeutet der Ausdruck „geordnet“, dass die Reihenfolge, in der Elemente eingefügt und gelöscht werden, deren Reihenfolge in der Auflistung bestimmt. Es bedeutet nicht, dass die Elemente anhand ihres Inhalts sortiert werden. Der Begriff „indiziert“ bedeutet, dass die Elemente in der Auflistung über einen Ganzzahlenindex, ähnlich wie die Elemente in einem normalen Array, abgerufen werden können.

- Spalten 4 und 5 werden die Leistung für jede Klasse beschrieben. In Anwendungen, die viele Einfügungen in die Auflistung erfordern, ist möglicherweise die Einfügungsgeschwindigkeit besonders wichtig; für andere Programme könnte die Suchgeschwindigkeit wichtiger sein.

- In Spalte 6 wird beschrieben, ob die einzelnen Formen doppelte Elemente zulassen.

- Die Leistung einer bestimmten Sammlung-Klasse-Operation wird in Bezug auf die Beziehung zwischen den Zeitaufwand zum Abschließen des Vorgangs und die Anzahl der Elemente in der Auflistung angegeben. Ein Vorgang einen Anteil der Zeit zunimmt, die linear wie die wachsender Anzahl von Elementen als ein o(n)-Algorithmus beschrieben wird. Im Gegensatz dazu wird ein Vorgang eine bestimmte Zeitspanne, die kleiner als die Anzahl der Elemente steigt vergrößert als einen Algorithmus O (Log n) beschrieben. Aus diesem Grund wird im Hinblick auf Leistung, O (Log n) Algorithmen O(n) Algorithmen mehr und mehr als die Anzahl der Elemente steigt übertreffen.

### <a name="collection-shape-features"></a>Auflistungsformfeatures

|Form|Geordnete|Indiziert|Fügen Sie ein<br /><br /> Element|Suchen nach<br /><br /> angegebene element|Duplizieren<br /><br /> Elemente|
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|
|Liste|Ja|Nein|Schnell (Konstante Zeit)|Langsam O(n)|Ja|
|Array|Ja|Nach Ganzzahl (Konstante Zeit)|Langsam O(n), außer wenn am Ende einfügen, in konstanter Zeit und die Groß-/Kleinschreibung|Langsam O(n)|Ja|
|Zuordnung|Nein|Nach Schlüssel (Konstante Zeit)|Schnell (Konstante Zeit)|Schnell (Konstante Zeit)|Nein (Schlüssel) Ja (Werte)|
|Rot-Schwarz-Karte|Ja (per Schlüssel)|Nach Schlüssel O (Log n)|Schnelle O (Log n)|Schnelle O (Log n)|Nein|
|Rot-Schwarz-Mehrfachzuordnung|Ja (per Schlüssel)|Nach Schlüssel O(log n) (mehrere Werte pro Schlüssel)|Schnelle O (Log n)|Schnelle O (Log n)|Ja (mehrere Werte pro Schlüssel)|

## <a name="using-ctraits-objects"></a>Verwenden von CTraits-Objekten

Wie die ATL-Auflistungsklassen verwendet werden können, um eine Vielzahl von benutzerdefinierten Datentypen speichern, kann es sinnvoll, wichtige Funktionen wie z. B. Vergleiche überschreiben sein. Dies erfolgt mithilfe der CTraits-Klassen.

CTraits-Klassen sind ähnlich, aber viel flexibler als die Klasse-Hilfsfunktionen für MFC-Auflistung. finden Sie unter [Auflistungsklasse](../mfc/reference/collection-class-helpers.md) für Weitere Informationen.

Wenn Sie Ihre Auflistungsklasse erstellen zu können, müssen Sie die Option zum Angeben einer CTraits-Klasse. Diese Klasse enthält den Code, der Vorgänge, z. B. Vergleiche, wenn von den anderen Methoden aufgerufen werden soll, aus denen die Auflistungsklasse ausführen wird. Z. B. wenn das Listenobjekt eigene benutzerdefinierte Strukturen enthält, sollten Sie so definieren, um den Gleichheitstest auf, um nur bestimmte Membervariablen des Typs zu vergleichen. Auf diese Weise werden die Find-Methode für das List-Objekt auf nützliche Weise ausgeführt.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

[!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]

## <a name="comments"></a>Kommentare

Eine Liste der CTraits-Klassen, finden Sie unter [Auflistungsklassen](../atl/collection-classes.md).

Das folgende Diagramm zeigt die Klassenhierarchie für die CTraits-Klassen.

![Merkmalhierarchie für Auflistungsklassen](../atl/media/vctraitscollectionclasseshierarchy.gif "merkmalhierarchie für Auflistungsklassen")

## <a name="collection-classes-samples"></a>Beispiele für Auflistungsklassen

Die folgenden Beispiele veranschaulichen die Auflistungsklassen:

- [MMXSwarm-Beispiel](../overview/visual-cpp-samples.md)

- [-Beispiel-Beispiel](../overview/visual-cpp-samples.md)

- [UpdatePV-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

- [Marquee-Beispiel](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[Auflistungsklassen](../atl/collection-classes.md)
