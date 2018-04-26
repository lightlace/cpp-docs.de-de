---
title: Überladen des &gt;&gt;-Operators für eigene Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 594a01b6d7cd0af7e27e02dcd3221c8e021402b4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
