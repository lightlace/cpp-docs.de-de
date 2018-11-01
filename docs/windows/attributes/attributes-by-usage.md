---
title: Attribute nach Verwendung
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: 2536309025506ca66d9c4b7cdfbaabf5787945e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449364"
---
# <a name="attributes-by-usage"></a>Attribute nach Verwendung

Dieses Thema enthält Attribute gemäß der Sprachelemente von C++ für die sie gelten.

Wenn ein Attribut ein Elements, das nicht im Bereich für das Attribut ist vorangeht, wird der Attributblock als Kommentar behandelt.

|Attribut|Beschreibung|
|---------------|-----------------|
|[Modulattribute](module-attributes.md)|Gilt für die [Modul](module-cpp.md) Attribut.|
|[Schnittstellenattribut](interface-attributes.md)|Gilt für die [__interface](../../cpp/interface.md) C++-Schlüsselwort.|
|[Klassenattribute](class-attributes.md)|Gilt für die C++-Schlüsselwort.|
|[Methodenattribut](method-attributes.md)|Gilt für die Methoden in einer Klasse, Co-Klasse oder Schnittstelle.|
|[Parameterattribute](parameter-attributes.md)|Gilt für den Parameter einer Methode in einer Klasse oder Schnittstelle.|
|[Datenmemberattribute](data-member-attributes.md)|Gilt für Datenmember einer Klasse, Co-Klasse oder Schnittstelle.|
|[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)|Gilt für die C++-Schlüsselwörter.|
|[Arrayattribute](array-attributes.md)|Gilt für Arrays oder `SAFEARRAY`s.|
|[Eigenständige Attribute](stand-alone-attributes.md)|Funktioniert ähnlich wie eine einzige Zeile Code arbeitet jedoch nicht auf ein C++-Schlüsselwort. Eigenständige Attribut-Anweisungen erfordern ein Semikolon am Ende der Zeile.|
|[Benutzerdefinierte Attribute](custom-attributes-cpp.md)|Ermöglicht dem Benutzer um Metadaten zu erweitern.|

## <a name="module-attributes"></a>Modulattribute
Das folgende Attribut kann nur angewendet werden, um die [Modul](module-cpp.md) Attribut.

|Attribut|Beschreibung|
|---------------|-----------------|
|[helpstringdll](helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|

## <a name="interface-attributes"></a>Schnittstellenattribut

Die folgenden Attribute gelten für die [-Schnittstelle (oder __interface)](../../cpp/interface.md) C++-Schlüsselwort.

|Attribut|Beschreibung|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|Gibt an, die UUID, die den MIDL-Compiler definiert synchrone und asynchrone Versionen einer COM-Schnittstelle weiterleitet.|
|[custom](custom-cpp.md)|Können Sie eigene Attribute definieren.|
|[dispinterface](dispinterface.md)|Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.|
|[dual](dual.md)|Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle an.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[helpcontext](helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|
|[helpfile](helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|
|[helpstring](helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|
|[helpstringcontext](helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|
|[helpstringdll](helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|
|[hidden](hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[library_block](library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[local](local-cpp.md)|Ermöglicht Ihnen die Verwendung den MIDL-Compiler als ein Header-Generator, wenn in der Schnittstelle-Header verwendet. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.|
|[nonextensible](nonextensible.md)|Gibt an, dass die `IDispatch` -Implementierung enthält nur die Eigenschaften und Methoden aufgeführt, die in der schnittstellenbeschreibung und können nicht zur Laufzeit zusätzliche Member erweitert werden. Dieses Attribut ist nur gültig für eine [dual](dual.md) Schnittstelle.|
|[odl](odl.md)|Gibt eine Schnittstelle als Schnittstelle Objekt Description Language (ODL).|
|[object](object-cpp.md)|Gibt eine benutzerdefinierte Schnittstelle an.|
|[oleautomation](oleautomation.md)|Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.|
|[pointer_default](pointer-default.md)|Gibt das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die angezeigt werden in der Parameterliste.|
|[ptr](ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|
|[restricted](restricted.md)|Legt fest, welche Elemente der Bibliothek nicht beliebig aufgerufen werden können.|
|[uuid](uuid-cpp-attributes.md)|Stellt die eindeutige ID für die Bibliothek|

Sie müssen diese Regeln zum Definieren einer Schnittstelle beachten:

- Standardaufrufkonvention ist [__stdcall](../../cpp/stdcall.md).

- Eine GUID wird für Sie bereitgestellt werden, wenn Sie eine nicht angeben.

- Es sind keine überladenen Methoden zulässig.

Wenn Sie nicht angeben der [Uuid](uuid-cpp-attributes.md) Attribut, und verwenden den gleichen Schnittstellennamen in Projekten auf anderes Attribut, wird dieselbe GUID generiert.

## <a name="see-also"></a>Siehe auch

[C++-Attribute für COM und .NET](cpp-attributes-com-net.md)<br/>
[Attribute nach Gruppen](attributes-by-group.md)<br/>
[Alphabetische Attributreferenz](attributes-alphabetical-reference.md)