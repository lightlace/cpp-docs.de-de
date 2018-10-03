---
title: Schreiben eigener Manipulatoren ohne Argumente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8bfad1919863a58554604fe6d32b4563e57a14a
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235710"
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

[Ausgabestreams](../standard-library/output-streams.md)<br/>
