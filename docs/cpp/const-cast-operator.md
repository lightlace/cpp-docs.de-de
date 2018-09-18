---
title: Const_cast-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 314e8363fafa4f2a6649055f2c608cd5b7edd18c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070079"
---
# <a name="constcast-operator"></a>const_cast-Operator

Entfernt die **const**, **flüchtige**, und **__unaligned** -Attribute aus einer Klasse.

## <a name="syntax"></a>Syntax

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Hinweise

Ein Zeiger auf einen beliebigen Objekttyp oder ein Zeiger auf einen Datenmember explizit umgewandelt werden kann ein Typ, der identisch ist die **const**, **flüchtige**, und **__unaligned** Qualifizierer. Für Zeiger und Verweise verweist das Ergebnis auf das ursprüngliche Objekt. Für Zeiger auf Datenmember, verweist das Ergebnis auf denselben Member wie der ursprüngliche (uncast) Zeiger auf Datenmember. Je nach Typ des verweisenden Objekts, führt ein Schreibvorgang durch den resultierenden Zeiger, Verweis oder Zeiger auf Datenmember möglicherweise zu nicht definiertem Verhalten.

Sie können keine der **"const_cast"** Operator, um den Konstanten Status einer Konstanten Variable direkt zu überschreiben.

Die **"const_cast"** -Operator konvertiert einen null-Zeiger-Wert, der null-Zeigerwert des Zieltyps.

## <a name="example"></a>Beispiel

```cpp
// expre_const_cast_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CCTest {
public:
   void setNumber( int );
   void printNumber() const;
private:
   int number;
};

void CCTest::setNumber( int num ) { number = num; }

void CCTest::printNumber() const {
   cout << "\nBefore: " << number;
   const_cast< CCTest * >( this )->number--;
   cout << "\nAfter: " << number;
}

int main() {
   CCTest X;
   X.setNumber( 8 );
   X.printNumber();
}
```

In der Zeile mit der **"const_cast"**, der Datentyp des der **dies** Zeiger `const CCTest *`. Die **"const_cast"** Operator ändert den Datentyp des der **dies** Zeiger auf `CCTest *`, sodass das Element `number` geändert werden. Die Umwandlung erfolgt nur für den Rest der Anweisung, in der er angezeigt wird.

## <a name="see-also"></a>Siehe auch

[Umwandlungsoperatoren](../cpp/casting-operators.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)