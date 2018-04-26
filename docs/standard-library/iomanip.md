---
title: '&lt;iomanip&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
dev_langs:
- C++
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ced350154aefeb46442ef78f534cce86b312057b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Enthalten die `iostreams` Standardheader \<Iomanip > um verschiedene Manipulatoren zu definieren, da jedes akzeptieren ein einzelnes Argument.

## <a name="syntax"></a>Syntax

```cpp
#include <iomanip>

```

## <a name="remarks"></a>Hinweise

Jeder dieser Manipulatoren gibt einen nicht angegebenen Typ zurück, die **T1** bis **T10** genannt werden. Diese überladen `basic_istream`\<**Elem**, **Tr**>`::`[operator>>](../standard-library/istream-operators.md#op_gt_gt) und `basic_ostream`\<**Elem**, **Tr**>`::`[operator<<](../standard-library/ostream-operators.md#op_lt_lt).

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
