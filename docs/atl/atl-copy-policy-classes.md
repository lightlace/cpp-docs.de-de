---
title: ATL-Kopierrichtlinienklasse
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 535bd1a3129bab15f546f6a82d77cf4e152fc605
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452753"
---
# <a name="atl-copy-policy-classes"></a>ATL-Kopierrichtlinienklasse

Kopierrichtlinienklasse sind [hilfsprogrammklassen](../atl/utility-classes.md) zum Initialisieren verwendet, kopieren und Löschen von Daten. Kopierrichtlinienklasse können Sie die Kopiersemantik für jede Art von Daten zu definieren und Konvertierungen zwischen verschiedenen Datentypen definieren.

ATL-verwendet Kopierrichtlinienklasse in seinen Implementierungen der folgenden Vorlagen:

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

Durch kapseln die erforderlichen Informationen zum Kopieren, oder Konvertieren von Daten in einer Klasse der kopieren-Richtlinie, die als Vorlagenargument übergeben werden kann, haben die ATL-Entwickler für extreme wiederverwendbarkeit dieser Klassen bereitgestellt. Wenn Sie eine Sammlung über einen beliebigen Datentyp implementieren müssen, alles, was Sie bereitstellen müssen ist beispielsweise die Kopierrichtlinie für die entsprechende; Sie müssen nicht den Code zu ändern, der die Auflistung implementiert.

## <a name="definition"></a>Definition

Definitionsgemäß ist eine Klasse, die folgenden statischen Funktionen bietet, einer Kopierrichtlinienklasse:

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

Sie können die Typen ersetzen `DestinationType` und *SourceType* mit beliebigen Datentypen für jede Kopierrichtlinie.

> [!NOTE]
>  Obwohl Sie Kopierrichtlinienklasse für beliebige Datentypen definieren können, sollten Verwendung der Klassen in ATL-Code die Typen beschränken, die sinnvoll. Z. B. wenn mithilfe einer Kopierrichtlinie die Klasse mit ATLs-Auflistungen oder Enumerator Implementierungen `DestinationType` muss ein Typ, der als Parameter in COM-Schnittstellenmethode verwendet werden kann.

Verwendung **Init** so initialisieren Sie Daten, **Kopie** zum Kopieren von Daten, und **zerstören** , Daten freizugeben. Die genaue Bedeutung von Initialisierung, kopieren und Löschen der Domäne der kopieren-Policy-Klasse und variiert abhängig von den beteiligten Datentypen.

Es gibt zwei Anforderungen für die Verwendung und Implementierung von einer Kopierrichtlinienklasse:

- Der erste Parameter für **Kopie** muss nur einen Zeiger auf Daten, die Sie zuvor initialisiert haben mit empfangen **Init**.

- **Zerstören** empfangen müssen immer nur einen Zeiger auf Daten, die Sie zuvor initialisiert haben mit **Init** oder kopierte über **Kopie**.

## <a name="standard-implementations"></a>Standard-Implementierungen

ATL stellt zwei Kopierrichtlinienklasse in Form von der `_Copy` und `_CopyInterface` Vorlagenklassen:

- Die `_Copy` Klasse ermöglicht homogene nur kopiert werden (nicht-Konvertierung zwischen Datentypen), da es nur einen einzelner Vorlagenparameter zum Angeben bietet `DestinationType` und *SourceType*. Die generische Implementierung dieser Vorlage enthält keinen Initialisierungs- oder Zerstörung Code und verwendet `memcpy` zum Kopieren der Daten. ATL bietet auch spezialisierungen `_Copy` für Variant-Wert, LPOLESTR, OLEVERB und CONNECTDATA-Datentypen.

- Die `_CopyInterface` -Klasse stellt eine Implementierung für das Kopieren der folgenden Standardregeln COM-Schnittstellenzeiger. Wieder mit dieser Klasse können nur homogene kopieren, verwendet einfache Zuweisung und einem Aufruf von `AddRef` zum Durchführen des Kopiervorgangs.

## <a name="custom-implementations"></a>Benutzerdefinierte Implementierungen

In der Regel müssen Sie Ihre eigenen Kopierrichtlinienklassen für heterogene kopieren (d. h. die Konvertierung zwischen Datentypen) zu definieren. Betrachten Sie einige Beispiele von benutzerdefinierten Kopierrichtlinienklassen Dateien VCUE_Copy.h und VCUE_CopyString.h in die [ATLCollections](../visual-cpp-samples.md) Beispiel. Diese Dateien enthalten zwei Vorlage Kopierrichtlinienklassen, `GenericCopy` und `MapCopy`, sowie eine Anzahl von spezialisierungen `GenericCopy` für verschiedene Datentypen.

### <a name="genericcopy"></a>GenericCopy

`GenericCopy` ermöglicht Ihnen die Angabe der *SourceType* und `DestinationType` als Vorlagenargumente. Hier ist die allgemeinste Form der `GenericCopy` Klasse von VCUE_Copy.h:

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy.h enthält auch die folgenden spezialisierungen dieser Klasse: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`. VCUE_CopyString.h enthält spezialisierungen für das Kopieren von **Std:: String**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, und `GenericCopy<BSTR, std::string>`. Sie verbessern können `GenericCopy` durch die Bereitstellung Weitere spezialisierungen von Ihren eigenen.

### <a name="mapcopy"></a>MapCopy

`MapCopy` wird davon ausgegangen, dass die kopierten Daten in eine C++-Standard-Bibliothek-Style-Zuordnung gespeichert werden, so können Sie den Typ der Karte angeben, in dem die Daten werden gespeichert, und geben Sie das Ziel. Die Implementierung der Klasse verwendet die Typdefinitionen, die vom der *MapType* Klasse, um den Typ der Quelldaten zu ermitteln und den entsprechenden Aufrufen `GenericCopy` Klasse. Es werden keine spezialisierungen dieser Klasse benötigt.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>Siehe auch

[Implementieren einer auf der C++-Standardbibliothek basierten Auflistung](../atl/implementing-an-stl-based-collection.md)<br/>
[-Beispiel](../visual-cpp-samples.md)

