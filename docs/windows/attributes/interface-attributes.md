---
title: Schnittstellenattribut (C++-COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
ms.openlocfilehash: 8218ccb66c6be9edef5d7de751a73bf4753d069f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027204"
---
# <a name="interface-attributes"></a>Schnittstellenattribut

Die folgenden Attribute gelten für die [-Schnittstelle (oder __interface)](../../cpp/interface.md) C++ Schlüsselwort.

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

[Attribute nach Verwendung](attributes-by-usage.md)