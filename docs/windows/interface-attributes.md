---
title: Schnittstellenattribut | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 850646e2dda1f226eff7c921dd3fe9f85595ca69
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317653"
---
# <a name="interface-attributes"></a>Schnittstellenattribut

Die folgenden Attribute gelten für die [-Schnittstelle (oder __interface)](../cpp/interface.md) C++-Schlüsselwort.

|Attribut|Beschreibung|
|---------------|-----------------|
|[async_uuid](../windows/async-uuid.md)|Gibt an, die UUID, die den MIDL-Compiler definiert synchrone und asynchrone Versionen einer COM-Schnittstelle weiterleitet.|
|[Benutzerdefinierte](../windows/custom-cpp.md)|Können Sie eigene Attribute definieren.|
|[dispinterface](../windows/dispinterface.md)|Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.|
|[dual](../windows/dual.md)|Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle an.|
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[library_block](../windows/library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[local](../windows/local-cpp.md)|Ermöglicht Ihnen die Verwendung den MIDL-Compiler als ein Header-Generator, wenn in der Schnittstelle-Header verwendet. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.|
|[nonextensible](../windows/nonextensible.md)|Gibt an, dass die `IDispatch` -Implementierung enthält nur die Eigenschaften und Methoden aufgeführt, die in der schnittstellenbeschreibung und können nicht zur Laufzeit zusätzliche Member erweitert werden. Dieses Attribut ist nur gültig für eine [dual](../windows/dual.md) Schnittstelle.|
|[odl](../windows/odl.md)|Gibt eine Schnittstelle als Schnittstelle Objekt Description Language (ODL).|
|[object](../windows/object-cpp.md)|Gibt eine benutzerdefinierte Schnittstelle an.|
|[oleautomation](../windows/oleautomation.md)|Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.|
|[pointer_default](../windows/pointer-default.md)|Gibt das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die angezeigt werden in der Parameterliste.|
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|
|[restricted](../windows/restricted.md)|Legt fest, welche Elemente der Bibliothek nicht beliebig aufgerufen werden können.|
|[uuid](../windows/uuid-cpp-attributes.md)|Stellt die eindeutige ID für die Bibliothek|

Sie müssen diese Regeln zum Definieren einer Schnittstelle beachten:

- Standardaufrufkonvention ist [__stdcall](../cpp/stdcall.md).

- Eine GUID wird für Sie bereitgestellt werden, wenn Sie eine nicht angeben.

- Es sind keine überladenen Methoden zulässig.

Wenn Sie nicht angeben der [Uuid](../windows/uuid-cpp-attributes.md) Attribut, und verwenden den gleichen Schnittstellennamen in Projekten auf anderes Attribut, wird dieselbe GUID generiert.

## <a name="see-also"></a>Siehe auch

[Attribute nach Verwendung](../windows/attributes-by-usage.md)