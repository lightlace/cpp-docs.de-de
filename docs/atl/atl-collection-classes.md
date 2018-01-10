---
title: ATL-Auflistungsklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24b0fbdc5ab68319704fb59746862384198f232b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-collection-classes"></a>ATL-Auflistungsklassen
ATL stellt zahlreiche Klassen zum Speichern und Zugreifen auf Daten bereit. Welche Klasse, die Sie verwenden möchten, hängt von mehreren Faktoren ab, einschließlich ab:  
  
-   Die Menge der Daten gespeichert werden  
  
-   Effizienz und Leistung beim Zugriff auf die Daten  
  
-   Die Möglichkeit für den Datenzugriff nach Index oder Schlüssel  
  
-   Wie die Daten sortiert werden  
  
-   Persönlichen Vorlieben  
  
## <a name="small-collection-classes"></a>Kleine Auflistungsklassen  
 ATL stellt die folgenden Klassen für Arrays, für den Umgang mit einer kleinen Anzahl von Objekten. Diese Klassen sind jedoch eingeschränkt und intern entwickelt für die Verwendung von ATL Es wird nicht empfohlen, dass Sie sie in Ihren Programmen verwenden.  
  
|Klasse|Typ der datenspeicherung|  
|-----------|--------------------------|  
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Eine Arrayklasse für den Umgang mit einer kleinen Anzahl von Objekten implementiert.|  
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Eine Zuordnungsklasse für den Umgang mit einer kleinen Anzahl von Objekten implementiert.|  
  
## <a name="general-purpose-collection-classes"></a>Allgemeine Batchinstanzen-Auflistungsklassen  
 Die folgenden Klassen implementieren, Arrays, Listen und Zuordnungen und dienen als Auflistungsklassen für allgemeine Zwecke:  
  
|Klasse|Typ der datenspeicherung|  
|-----------|--------------------------|  
|[CAtlArray](../atl/reference/catlarray-class.md)|Implementiert ein Array.|  
|[CAtlList](../atl/reference/catllist-class.md)|Implementiert eine Liste an.|  
|[CAtlMap](../atl/reference/catlmap-class.md)|Implementiert eine Zuordnungsstruktur, bei dem Daten nach Schlüssel oder Wert verwiesen werden kann.|  
|[CRBMap](../atl/reference/crbmap-class.md)|Implementiert eine Zuordnungsstruktur mithilfe des Algorithmus Rot Schwarz.|  
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Implementiert eine Multimappingstruktur Rot Schwarz.|  
  
 Diese Klassen werden viele Programmierfehler, bei der Verwendung in der Debug-Builds abfangen, aber zur besseren Übersichtlichkeit Leistung zu erzielen, werden diese Überprüfungen nicht in Verkaufsversionen ausgeführt werden.  
  
## <a name="specialized-collection-classes"></a>Spezialisierte Auflistungsklassen  
 Spezialisiertere Auflistungsklassen werden auch zum Verwalten von Speicherzeigern und Schnittstellenzeigern bereitgestellt:  
  
|Klasse|Zweck|  
|-----------|-------------|  
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Stellt Methoden bereit, wenn ein Array von intelligenten Zeigern zu erstellen.|  
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Stellt Methoden bereit, beim Erstellen einer Liste von intelligenten Zeigern.|  
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|Speichert `IUnknown` Zeiger als Parameter verwendet werden soll, und die [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.|  
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Stellt Methoden bereit, bei der eine Liste von Zeigern Heap erstellen.|  
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|Stellt Methoden bereit, bei der ein Array von COM-Schnittstellenzeigern erstellen.|  
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|Stellt Methoden bereit, beim Erstellen einer Liste von COM-Schnittstellenzeigern.|  
  
## <a name="choosing-a-collection-class"></a>Auswahl einer Sammlungsklasse  
 Jede der verfügbaren Auflistungsklassen bietet unterschiedlichen Leistungsmerkmalen, wie in der folgenden Tabelle gezeigt.  
  
-   Spalten 2 und 3 werden jeder Klasse die Reihenfolge- und Zugriffsmerkmale. In der Tabelle bedeutet der Ausdruck „geordnet“, dass die Reihenfolge, in der Elemente eingefügt und gelöscht werden, deren Reihenfolge in der Auflistung bestimmt. Es bedeutet nicht, dass die Elemente anhand ihres Inhalts sortiert werden. Der Begriff „indiziert“ bedeutet, dass die Elemente in der Auflistung über einen Ganzzahlenindex, ähnlich wie die Elemente in einem normalen Array, abgerufen werden können.  
  
-   Spalten 4 und 5 werden die Leistung für jede Klasse beschrieben. In Anwendungen, die viele Einfügungen in die Auflistung erfordern, ist möglicherweise die Einfügungsgeschwindigkeit besonders wichtig; für andere Programme könnte die Suchgeschwindigkeit wichtiger sein.  
  
-   In Spalte 6 wird beschrieben, ob die einzelnen Formen doppelte Elemente zulassen.  
  
-   Die Leistung eines bestimmten Sammlung Klasse wird im Hinblick auf die Beziehung zwischen der Zeitaufwand zum Abschließen des Vorgangs und die Anzahl der Elemente in der Auflistung angegeben werden. Ein Vorgang dauert eine Zeitspanne zunimmt, linear wie die Anzahl der Elemente erhöht als einen o(n)-Algorithmus beschrieben wird. Im Gegensatz dazu, wird ein Vorgang eine bestimmte Zeitspanne, die kleiner als die Anzahl von Elementen vergrößert dauert als einen Algorithmus O (Log n) beschrieben. Aus diesem Grund übertreffen O (Log n) Algorithmen hinsichtlich der Leistung O(n) Algorithmen mehr und mehr als die Anzahl der Elemente erhöht.  
  
### <a name="collection-shape-features"></a>Auflistungsformfeatures  
  
|Form|Geordnete|Indiziert|Fügen Sie ein<br /><br /> Element|Suchen nach<br /><br /> das angegebene element|Duplizieren<br /><br /> Elemente|  
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|  
|Liste|Ja|Nein|Fast (Konstante Zeit)|Langsam O(n)|Ja|  
|Array|Ja|Nach Ganzzahl (Konstante Zeit)|Langsam O(n), außer wenn Einfügen am Ende, in der Groß-/Kleinschreibung konstanter Zeit|Langsam O(n)|Ja|  
|Zuordnung|Nein|Nach Schlüssel (Konstante Zeit)|Fast (Konstante Zeit)|Fast (Konstante Zeit)|Nein (Schlüssel) Ja (Werte)|  
|Rot Schwarz-Karte|Ja (nach Schlüssel)|Nach Schlüssel O (Log n)|Schnelle O (Log n)|Schnelle O (Log n)|Nein|  
|Rot Schwarz Mehrfachzuordnung|Ja (nach Schlüssel)|Durch Schlüssel O(log n) (mehrere Werte pro Schlüssel)|Schnelle O (Log n)|Schnelle O (Log n)|Ja (mehrere Werte pro Schlüssel)|  
  
## <a name="using-ctraits-objects"></a>Verwenden von CTraits-Objekten  
 Wie die ATL-Auflistungsklassen verwendet werden können, um eine Vielzahl von benutzerdefinierten Datentypen speichern, kann es nützlich sein, um wichtige Funktionen wie Vergleiche zu überschreiben sein. Dies erfolgt mithilfe der CTraits-Klassen.  
  
 CTraits-Klassen sind ähnlich, jedoch flexibler als die Hilfsfunktionen für MFC-Auflistung-Klasse. finden Sie unter [Auflistungsklasse](../mfc/reference/collection-class-helpers.md) für Weitere Informationen.  
  
 Wenn Sie Ihre Auflistungsklasse erstellen zu können, müssen Sie die Option zum Angeben einer CTraits-Klasse. Diese Klasse enthält den Code, der Vorgänge wird z. B. Vergleiche, die beim Aufruf durch die anderen Methoden, die die Auflistungsklasse bilden. Z. B. List-Objekt eine eigene benutzerdefinierte Strukturen enthält, können Sie die Gleichheitstest, um nur bestimmte Membervariablen vergleichen neu definieren möchten. Auf diese Weise kann das Listenobjekt Find-Methode auf eine weitere nützliche Weise ausgeführt werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
 [!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]  
  
## <a name="comments"></a>Kommentare  
 Eine Liste der CTraits-Klassen, finden Sie unter [Auflistungsklassen](../atl/collection-classes.md).  
  
 Das folgende Diagramm zeigt die Klassenhierarchie für die CTraits-Klassen.  
  
 ![Merkmalhierarchie für Auflistungsklassen](../atl/media/vctraitscollectionclasseshierarchy.gif "Vctraitscollectionclasseshierarchy")  
  
## <a name="collection-classes-samples"></a>Beispiele für Auflistungsklassen  
 Die folgenden Beispiele zeigen die Auflistungsklassen:  
  
-   [MMXSwarm-Beispiel](../visual-cpp-samples.md)  
  
-   [-Beispiel-Beispiel](../visual-cpp-samples.md)  
  
-   [UpdatePV-Beispiel](../visual-cpp-samples.md)  
  
-   [Laufschriften-Beispiel](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [Auflistungsklassen](../atl/collection-classes.md)

