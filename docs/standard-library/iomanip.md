---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: 983fbc190fb83b81534e3888c748c0bf9c235638
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524663"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Enthalten die `iostreams` Standardheader \<Iomanip > um verschiedene Manipulatoren zu definieren, die jeweils ein einzelnes Argument nutzen.

## <a name="syntax"></a>Syntax

```cpp
#include <iomanip>
```

## <a name="remarks"></a>Hinweise

Jeder dieser Manipulatoren gibt einen nicht angegebenen Typ, der Namen `T1` über `T10`, methodenüberladungen, die beide `basic_istream` \< **Elem**, **Tr** > `::` [Operator >>](../standard-library/istream-operators.md#op_gt_gt) und `basic_ostream` \< **Elem**, **Tr** > `::` [Operator <<](../standard-library/ostream-operators.md#op_lt_lt).

### <a name="manipulators"></a>Manipulatoren

|||
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|Ruft einen Geldbetrag ab, optional in einem internationalen Format.|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Ruft eine Uhrzeit in einer Zeitstruktur mithilfe eines angegebenen Formats ab.|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|Stellt einen Geldbetrag bereit, optional in einem internationalen Format.|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Stellt eine Uhrzeit in einer Zeitstruktur und eine Formatzeichenfolge für die Verwendung bereit.|
|[quoted](../standard-library/iomanip-functions.md#quoted)|Ermöglicht praktische Roundtrips von Zeichenfolgen mit „insertion“ und „extraction“-Operatoren.|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Löscht die angegebenen Flags.|
|[setbase](../standard-library/iomanip-functions.md#setbase)|Legt die Basis für Ganzzahlen fest.|
|[setfill](../standard-library/iomanip-functions.md#setfill)|Legt das zum Auffüllen in einer rechts ausgerichteten Anzeige verwendete Zeichen fest.|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Legt die angegebenen Flags fest.|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Legt die Genauigkeit für Gleitkommawerte fest.|
|[setw](../standard-library/iomanip-functions.md#setw)|Gibt die Breite des Anzeigefelds an.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
