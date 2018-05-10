---
title: Überladen des &gt;&gt;-Operators für eigene Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d98372009090b0241d9f0190a1d53a9416bbd7ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Überladen des &gt;&gt;-Operators für eigene Klassen

Eingabestreams verwenden die Extraktion (`>>`)-Operator für die Standardtypen. Sie können ähnliche Extraktionsoperatoren für eigene Typen schreiben. Der Erfolg hängt von der genauen Nutzung von Leerraum ab.

Hier ist ein Beispiel für einen Extraktionsoperator der `Date`-Klasse, wie vorher beschrieben:

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
