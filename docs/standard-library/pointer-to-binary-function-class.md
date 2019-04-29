---
title: pointer_to_binary_function-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 88d38be258c6ceb1054e0d31cc52e4d8d25186ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370319"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function-Klasse

Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion. Veraltet in C ++ 11, C ++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parameter

*pfunc*<br/>
Die binäre Funktion, die konvertiert werden soll.

*left*<br/>
Das linke Objekt, auf dem *\*pfunc* aufgerufen wird.

*right*<br/>
Das rechte Objekt, auf dem *\*pfunc* aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Die Vorlagenklasse speichert eine Kopie des `pfunc`. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert `(* pfunc)(Left, right)`.

## <a name="remarks"></a>Hinweise

Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine binäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Für die Verwendung mit einem Adapter, z.B. einen Wert zuzuordnen oder ihn mit einer Negator zu verwenden müssen sie die geschachtelten Typen angegeben werden `first_argument_type`, `second_argument_type`, und `result_type` , die solche Anpassung möglich machen. Die Konvertierung durch `pointer_to_binary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.

## <a name="example"></a>Beispiel

Der Konstruktor von `pointer_to_binary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_binary_function`-Adapterprädikats.

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
