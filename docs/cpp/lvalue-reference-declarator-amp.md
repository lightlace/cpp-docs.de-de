---
title: 'Lvalue-Verweisdeklarator: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 7710b6f1efc2de770b26ad50923bde2ee5200f61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209553"
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue-Verweisdeklarator: &amp;

Enthält die Adresse eines Objekts, verhält sich jedoch syntaktisch wie ein Objekt.

## <a name="syntax"></a>Syntax

```
type-id & cast-expression
```

## <a name="remarks"></a>Hinweise

Sie können sich einen lvalue-Verweis als einen anderen Namen für ein Objekt vorstellen. Eine lvalue-Verweisdeklaration enthält eine optionale Liste von Bezeichnern, gefolgt von einem Verweisdeklarator. Ein Verweis muss initialisiert werden und kann nicht geändert werden.

Jedes Objekt, dessen Adresse in einen angegebenen Zeigertyp konvertiert werden kann, kann auch in den ähnlichen Referenztyp konvertiert werden. Beispielsweise kann jedes Objekt, dessen Adresse in den Typ `char *` konvertiert werden kann, auch in den Typ `char &` konvertiert werden.

Verwechseln Sie Verweisdeklarationen mit Verwendung von nicht die [Address-of-Operator](../cpp/address-of-operator-amp.md). Wenn die `&` *Bezeichner* ist ein Typ vorangestellt, wie z. B. **Int** oder **Char**, *Bezeichner* deklariert wird, als Verweis auf Der Typ. Wenn `&` *Bezeichner* steht nicht von einem Typ, ist die Verwendung des Address-of-Operators.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt den Verweisdeklarator, indem ein `Person`-Objekt und ein Verweis auf dieses Objekt deklariert wird. Da `rFriend` ein Verweis auf `myFriend` ist, ändert die Aktualisierung einer der Variablen das gleiche Objekt.

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>Siehe auch

[Verweise](../cpp/references-cpp.md)<br/>
[Verweistyp-Funktionsargumente](../cpp/reference-type-function-arguments.md)<br/>
[Verweistyp-Funktionsrückgaben](../cpp/reference-type-function-returns.md)<br/>
[Verweise auf Zeiger](../cpp/references-to-pointers.md)