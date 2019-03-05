---
title: Implementieren einer C++-Standard Standardbibliothek basierten Auflistung
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 90583f34c9e9fb500bb48fdbd3c1a17d343d865f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292921"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>Implementieren einer C++-Standard Standardbibliothek basierten Auflistung

ATL stellt die `ICollectionOnSTLImpl` Schnittstelle, um C++-Standardbibliothek basierten Auflistungsschnittstellen schnell auf Ihre Objekte implementieren können. Um zu verstehen, wie diese Klasse funktioniert, arbeiten Sie über ein einfaches Beispiel (siehe unten), die diese Klasse verwendet, um eine schreibgeschützte Auflistung, die zur Benutzeroberflächenautomatisierungs-Clients zu implementieren.

Der Beispielcode stammt aus dem [-Beispiel](../visual-cpp-samples.md).

Um dieses Verfahren ausführen zu können, führen Sie folgende Aktionen ausführen:

- [Generieren Sie ein neues Objekt für die einfache](#vccongenerating_an_object).

- [Bearbeiten Sie die IDL-Datei](#vcconedit_the_idl) für die generierte Schnittstelle.

- [Erstellen von fünf Typdefinitionen](#vcconstorage_and_exposure_typedefs) beschreiben, wie die Elemente der Auflistung gespeichert werden und wie sie für Clients über COM-Schnittstellen verfügbar gemacht werden.

- [Erstellen Sie zwei Typdefinitionen für das Kopieren richtlinienklassen](#vcconcopy_classes).

- [Erstellen Sie die Typdefinitionen für Implementierungen der Enumerator und Auflistung](#vcconenumeration_and_collection).

- [Bearbeiten Sie den Assistenten generierte C++-Code zur Verwendung von Typedef Auflistung](#vcconedit_the_generated_code).

- [Hinzufügen von Code zum Auffüllen der Auflistung](#vcconpopulate_the_collection).

##  <a name="vccongenerating_an_object"></a> Generieren ein neues Objekt für die einfache

Erstellen Sie ein neues Projekt, um sicherzustellen, dass das Feld "Attribute" unter "Einstellungen"-Anwendung deaktiviert ist. Verwenden Sie das Dialogfeld "ATL-Klasse hinzufügen" und hinzufügen Assistent für einfache Objekte generieren Sie ein einfaches Objekt namens `Words`. Stellen Sie sicher, dass eine duale Schnittstelle aufgerufen `IWords` wird generiert. Objekte der generierten Klasse werden zum Darstellen einer Auflistung von Wörtern (d. h. Zeichenfolgen) verwendet werden.

##  <a name="vcconedit_the_idl"></a> Bearbeiten die IDL-Datei

Öffnen Sie jetzt die IDL-Datei und fügen Sie die drei Eigenschaften erforderlich, um aktivieren `IWords` in eine schreibgeschützte Auflistung-Schnittstelle, wie unten dargestellt:

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

Dies ist das Standardformat für die eine schreibgeschützte Auflistung-Schnittstelle, die speziell für Automatisierungsclients Bedenken. Die nummerierten Kommentare in diesen Schnittstellendefinition entsprechen den unten stehenden Kommentaren:

1. Collection-Schnittstellen sind in der Regel zwei, da Benutzeroberflächenautomatisierungs-Clients greift auf die `_NewEnum` Eigenschaft mithilfe des `IDispatch::Invoke`. Allerdings können Automatisierungsclients die verbleibenden Methoden über Vtable zugreifen, duale Schnittstellen, Dispatchschnittstellen vorzuziehen sind.

1. Wenn eine duale Schnittstelle oder Disp-Schnittstelle nicht zur Laufzeit erweitert wird (d. h. Sie wird nicht angeben, zusätzlichen Methoden oder Eigenschaften über `IDispatch::Invoke`), gelten die **nonextensible** -Attribut auf die Definition. Mit diesem Attribut können Automatisierungsclients zum Ausführen der Überprüfung der vollständigen Code zum Zeitpunkt der Kompilierung. In diesem Fall sollte die Schnittstelle nicht erweitert werden.

1. Die richtige DISPID ist wichtig, wenn Sie möchten, dass Benutzeroberflächenautomatisierungs-Clients, um diese Eigenschaft verwenden zu können. (Beachten Sie, dass nur ein Unterstrich in DISPID_NEWENUM vorhanden ist.)

1. Sie können einen beliebigen Wert angeben, wie die DISPID eines der `Item` Eigenschaft. Allerdings `Item` verwendet in der Regel DISPID_VALUE, erleichtern die Standardeigenschaft der Auflistung. Dadurch können Benutzeroberflächenautomatisierungs-Clients, auf die Eigenschaft zu verweisen, ohne explizit zu benennen.

1. Der Datentyp für den Rückgabewert verwendet die `Item` Eigenschaft ist der Typ des Elements in der Auflistung gespeichert werden, als COM-Clients betroffen sind. Die Schnittstelle gibt Zeichenfolgen zurück, daher sollten Sie den standardmäßigen COM-String-Datentyp, BSTR verwenden. Sie können die Daten intern in einem anderen Format speichern, wie Sie bald sehen werden.

1. Der Wert für die DISPID eines der `Count` Eigenschaft ist beliebig. Es gibt keine standardmäßige DISPID für diese Eigenschaft.

##  <a name="vcconstorage_and_exposure_typedefs"></a> Erstellen von Typdefinitionen für die Speicherung und Offenlegung

Nachdem die Auflistungsschnittstelle definiert ist, müssen Sie entscheiden, wie die Daten gespeichert werden sollen und wie die Daten über den Enumerator verfügbar gemacht werden.

Die Antworten auf diese Fragen können in Form einer Reihe von Typdefinitionen, bereitgestellt werden, die Sie am oberen Rand der Headerdatei für die neu erstellte Klasse hinzufügen können:

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

In diesem Fall speichern Sie die Daten als eine **Std:: vector** von **Std:: String**s. **Std:: vector** ist eine C++-Standardbibliothek-Container-Klasse, die sich wie ein verwaltetes Array verhält. **Std:: String** String-Klasse der C++-Standardbibliothek ist. Diese Klassen erleichtern die Arbeit mit der eine Auflistung von Zeichenfolgen.

Da Visual Basic-Unterstützung Schlüssel zum Erfolg dieser Schnittstelle ist, der Enumerator zurückgegebenes der `_NewEnum` Eigenschaft unterstützen, muss die `IEnumVARIANT` Schnittstelle. Dies ist die einzige Enumerator-Schnittstelle, die von Visual Basic verstanden.

##  <a name="vcconcopy_classes"></a> Erstellen von Typdefinitionen für Kopierrichtlinienklasse

Die Typdefinitionen, die Sie bisher erstellt haben alle die Informationen bereitstellen, müssen Sie weitere Typdefinitionen für die Copy-Klassen zu erstellen, die vom Enumerator und der Auflistung verwendet werden:

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

In diesem Beispiel können Sie die benutzerdefinierte `GenericCopy` Klasse VCUE_Copy.h und VCUE_CopyString.h von definiert die [ATLCollections](../visual-cpp-samples.md) Beispiel. Sie können diese Klasse verwenden, in einem anderen Code, jedoch müssen Sie möglicherweise genauer definieren, die spezialisierungen von `GenericCopy` zur Unterstützung von Datentypen, die in Ihren eigenen Sammlungen verwendet werden. Weitere Informationen finden Sie unter [ATL-Kopierrichtlinienklasse](../atl/atl-copy-policy-classes.md).

##  <a name="vcconenumeration_and_collection"></a> Erstellen von Typdefinitionen für die Enumeration und Sammlung

Jetzt alle Vorlagenparameter erforderlich, sind die `CComEnumOnSTL` und `ICollectionOnSTLImpl` Klassen in dieser Situation wurde bereitgestellt, in Form von Typdefinitionen. Um die Verwendung der spezialisierungen zu vereinfachen, erstellen Sie zwei weitere Typdefinitionen, wie unten dargestellt:

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

Jetzt `CollectionType` ist ein Synonym für eine Spezialisierung der `ICollectionOnSTLImpl` , implementiert die `IWords` Schnittstelle zuvor definiert haben, und stellt einen Enumerator bereit, dieser unterstützt `IEnumVARIANT`.

##  <a name="vcconedit_the_generated_code"></a> Bearbeiten den Assistenten generierte Code

Nachdem Sie ableiten müssen `CWords` aus der schnittstellenimplementierung, dargestellt durch die `CollectionType` Typedef statt `IWords`, wie unten dargestellt:

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

##  <a name="vcconpopulate_the_collection"></a> Hinzufügen von Code zum Auffüllen der Auflistung

Das einzige, die verbleibt, ist den Vektor mit Daten aufgefüllt. In diesem einfachen Beispiel können Sie ein paar Worte der Sammlung in den Konstruktor für die Klasse hinzufügen:

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

Jetzt können Sie den Code mit dem Client Ihrer Wahl testen.

## <a name="see-also"></a>Siehe auch

[Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)<br/>
[-Beispiel](../visual-cpp-samples.md)<br/>
[ATL-Kopierrichtlinienklasse](../atl/atl-copy-policy-classes.md)
