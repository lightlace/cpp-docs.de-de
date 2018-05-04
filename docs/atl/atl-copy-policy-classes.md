---
title: ATL-Kopierrichtlinienklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34b9ed5dca45633a5ab980d38b8a7cda151f5dc7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="atl-copy-policy-classes"></a>ATL-kopieren-Policy-Klassen
Kopie Richtlinienkopierklassen sind [hilfsprogrammklassen](../atl/utility-classes.md) zum Initialisieren verwendet, kopieren und Löschen von Daten. Kopierrichtlinienklassen können Sie die Semantik zum Kopieren für jeden Datentyp definieren und Konvertierungen zwischen verschiedenen Datentypen zu definieren.  
  
 ATL-verwendet, kopieren, Richtlinie die Klassen in ihre Implementierung der folgenden Vorlagen:  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 Durch das Kapseln der benötigten Informationen zum Kopieren oder konvertieren Sie Daten in einer Kopie-Policy-Klasse, die als Vorlagenargument übergeben werden kann, haben die ATL-Entwickler für extreme wiederverwendbarkeit dieser Klassen bereitgestellt. Wenn Sie eine Auflistung, die über einen beliebigen Datentyp implementieren müssen, alles, was Sie bereitstellen müssen ist beispielsweise die Kopierrichtlinie des entsprechenden; Sie müssen nie berühren Sie den Code, der die Auflistung implementiert.  
  
## <a name="definition"></a>Definition  
 Definitionsgemäß ist eine Klasse, die die folgenden statischen Funktionen einer Kopierrichtlinienklasse:  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 Sie können die Typen ersetzen `DestinationType` und *SourceType* mit beliebigen Datentypen für jede Kopierrichtlinie.  
  
> [!NOTE]
>  Zwar Kopierrichtlinienklassen für beliebige Datentypen definieren, sollten mithilfe der Klassen in ATL-Code die Typen beschränken, die sinnvoll sind. Z. B. wenn mithilfe einer Kopierrichtlinie für die die Klasse mit ATLs-Auflistung oder Enumerator Implementierungen `DestinationType` muss ein Typ, der als Parameter in einer COM-Schnittstellen-Methode verwendet werden kann.  
  
 Verwendung **Init** Daten initialisieren **kopieren** zum Kopieren von Daten, und **zerstören** Daten freigeben. Die genaue Bedeutung von Initialisierung, kopieren und Zerstörung der Domäne der kopieren-Richtlinienklasse und variiert abhängig von den beteiligten Datentypen.  
  
 Es gibt zwei Anforderungen für die Verwendung und Implementierung von einer Kopierrichtlinienklasse:  
  
-   Der erste Parameter für **Kopie** muss einen Zeiger auf Daten, die Sie zuvor initialisiert haben, verwenden nur empfangen **Init**.  
  
-   **Zerstören** muss einen Zeiger auf Daten, die Sie zuvor initialisiert haben, verwenden immer nur empfangen **Init** oder kopierte über **Kopie**.  
  
## <a name="standard-implementations"></a>Standard-Implementierungen  
 ATL stellt zwei Klassen der kopieren-Richtlinie in Form von den **"_Copy"** und **_CopyInterface** Vorlagenklassen:  
  
-   Die **"_Copy"** Klasse ermöglicht homogene nur kopieren (nicht-Konvertierung zwischen Datentypen), da es nur einen einzelnen Template-Parameter, um beide geben bietet `DestinationType` und *SourceType*. Die generische Implementierung dieser Vorlage enthält keinen Initialisierungs- oder Zerstörung Code und verwendet `memcpy` zum Kopieren der Daten. ATL stellt auch spezialisierungen **"_Copy"** für **VARIANT**, `LPOLESTR`, **OLEVERB**, und **CONNECTDATA** Datentypen.  
  
-   Die **_CopyInterface** -Klasse stellt eine Implementierung zum Kopieren von Schnittstellenzeigern standard-COM-Regeln folgen. Noch einmal mit dieser Klasse können nur homogene kopieren, daher einfache Zuweisung und einem Aufruf von `AddRef` für den Kopiervorgang.  
  
## <a name="custom-implementations"></a>Benutzerdefinierte Implementierungen  
 In der Regel müssen Sie eine eigene Kopierrichtlinienklassen für heterogene kopieren (d. h. die Konvertierung zwischen Datentypen) definieren. Betrachten Sie einige Beispiele für benutzerdefinierte Richtlinienkopierklassen, die Dateien VCUE_Copy.h und VCUE_CopyString.h in der [ATLCollections](../visual-cpp-samples.md) Beispiel. Diese Dateien enthalten zwei Kopie Richtlinie Vorlagenklassen, `GenericCopy` und `MapCopy`, sowie eine Anzahl von spezialisierungen `GenericCopy` für verschiedene Datentypen.  
  
### <a name="genericcopy"></a>GenericCopy  
 `GenericCopy` ermöglicht Ihnen das Festlegen der *SourceType* und `DestinationType` als Vorlagenargumente. Hier ist die allgemeinste Form der `GenericCopy` Klasse von VCUE_Copy.h:  
  
 [!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]  
  
 VCUE_Copy.h enthält außerdem die folgenden spezialisierungen dieser Klasse: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`. VCUE_CopyString.h enthält spezialisierungen für das Kopieren von **Std:: String**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, und `GenericCopy<BSTR, std::string>`. Sie verbessern können `GenericCopy` durch die Bereitstellung Weitere spezialisierungen Ihrer Wahl.  
  
### <a name="mapcopy"></a>MapCopy  
 `MapCopy` wird davon ausgegangen, dass die kopierten Daten in eine Zuordnung im C++-Standard-Bibliothek-Format gespeichert werden, so können Sie den Typ der Karte angeben, in dem die Daten gespeichert, und geben Sie das Ziel. Die Implementierung der Klasse verwendet nur bereitgestellt werden, indem Sie die *MapType* Klasse, um den Typ der Quelldaten zu bestimmen und den entsprechenden Aufrufen `GenericCopy` Klasse. Es werden keine spezialisierungen dieser Klasse benötigt.  
  
 [!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren einer C++-Standard-Library-basierte-Auflistung](../atl/implementing-an-stl-based-collection.md)   
 [-Beispiel](../visual-cpp-samples.md)

