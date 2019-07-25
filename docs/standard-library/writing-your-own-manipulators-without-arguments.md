---
title: Schreiben eigener Manipulatoren ohne Argumente
ms.date: 11/04/2016
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
ms.openlocfilehash: 9a1f72ae3e6860d8ab532a72a1776b77c7204f48
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450914"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Schreiben eigener Manipulatoren ohne Argumente

Das Schreiben von Manipulatoren, die keine Argumente verwenden, erfordert weder eine Klassenableitung noch die Verwendung von komplexen Makros. Angenommen, Ihr Drucker erfordert das Paar \<ESC>[, um in den Fettdruckmodus zu wechseln. Sie können dieses Paar direkt in den Stream einfügen:

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

Oder Sie können den `bold`-Manipulator definieren, der die Zeichen eingefügt:

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

Die global definierte `bold`-Funktion nimmt ein `ostream`-Verweisargument und gibt den `ostream`-Verweis zurück. Dabei handelt es sich um keine Member- oder Friend-Funktion, da kein Zugriff auf private Klassenelemente benötigt wird. Die `bold`-Funktion stellt eine Verbindung mit dem Stream her, da der `<<`-Operator des Streams überladen ist, um diesen Typ von Funktion zu akzeptieren, wobei eine Deklaration verwendet wird, die in etwa wie folgt aussieht:

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

Sie können diese Funktion verwenden, um andere überladene Operatoren zu erweitern. In diesem Fall fügt `bold` in der Folge Zeichen in den Stream ein. Die Funktion wird aufgerufen, wenn sie in den Stream eingefügt wird, nicht zwangsläufig beim Drucken der angrenzenden Zeichen. Folglich könnte es aufgrund der Streampufferung beim Drucken zu Verzögerungen kommen.

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)
