---
title: Grenzwerte für Gleitkommakonstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ea52c91391800b25ab9a71d977300dd1705fb51
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025528"
---
# <a name="floating-limits"></a>Grenzwerte für Gleitkommakonstanten

**Microsoft-spezifisch**

In der folgenden Tabelle sind die Limits für die Werte von Gleitkommakonstanten aufgeführt. Diese Grenzwerte werden auch in der Standardheaderdatei definiert \<float.h >.

## <a name="limits-on-floating-point-constants"></a>Grenzwerte für Gleitkommakonstanten

|Konstante|Bedeutung|Wert|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|Anzahl von Ziffern q, sodass eine Gleitkommazahl mit q Dezimalstellen ohne Genauigkeitsverlust auf eine Gleitkommadarstellung und zurück gerundet werden kann.|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|Kleinste positive Zahl x, sodass x + 1,0 ungleich 1,0 ist.|1.192092896e-07F<br/>2.2204460492503131e-016<br/>2.2204460492503131e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|Anzahl von Ziffern in der Basis von angegebenen `FLT_RADIX` in der gleitkommamantisse. Die Basis ist 2. Diese Werte geben daher Bits.|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|Darstellbare höchstgleitkommazahl.|3.402823466e+38F<br/>1.7976931348623158e+308<br/>1.7976931348623158e+308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|Maximale ganze Zahl, sodass 10 mit dieser Zahl potenziert eine darstellbare Gleitkommazahl ist.|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|Maximale ganze Zahl, `FLT_RADIX` potenziert mit dieser Zahl eine darstellbare Gleitkommazahl ist.|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|Minimaler positiver Wert.|1.175494351e-38F<br/>2.2250738585072014e-308<br/>2.2250738585072014e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|Minimal zulässige negative Ganzzahl, sodass 10 mit dieser Zahl potenziert eine darstellbare Gleitkommazahl ist.|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|Minimal zulässige negative Ganzzahl, `FLT_RADIX` potenziert mit dieser Zahl eine darstellbare Gleitkommazahl ist.|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|Basis der Exponentendarstellung.|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|Rundungsverhalten für gleitkommaaddition.|1 (ungefähr)<br/>1 (ungefähr)<br/>1 (ungefähr)|

> [!NOTE]
>  Die Informationen in der Tabelle können sich in zukünftigen Versionen des Produkts unterscheiden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Ganzzahlige Grenzen](../cpp/integer-limits.md)
