---
title: Compilerfehler C2243 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef5d3a6c20ff147ac2a4b765c7779cec9f19627e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102228"
---
# <a name="compiler-error-c2243"></a>Compilerfehler C2243

'Konvertierungstyp'-Konvertierung von 'Typ1' zu 'Typ2' ist vorhaden, jedoch kann darauf nicht zugegriffen werden

Zugriffsschutz (`protected` oder `private`) hat die Konvertierung von einem Zeiger in eine abgeleitete Klasse eines Zeiger in eine Basisklasse verhindert.

Das folgende Beispiel generiert C2243:

```
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

Basisklassen mit `protected`- oder `private`-Zugriff sind auf Clients der abgeleiteten Klasse nicht zugänglich. Diese Ebenen der Zugriffssteuerung werden verwendet, um anzugeben, dass die Basisklasse ein Implementierungsdetail ist, das für Clients nicht sichtbar sein sollte. Verwenden Sie die öffentliche Ableitung, wenn Sie möchten, dass Clients der abgeleiteten Klasse Zugriff auf die implizite Konvertierung eines abgeleiteten Klassenzeigers auf einen Zeiger auf die Basisklasse haben sollen.