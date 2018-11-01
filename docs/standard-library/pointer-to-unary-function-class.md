---
title: pointer_to_unary_function-Klasse
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: dc8a324d27870f615b810a3e86c355fadaf5c78d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558326"
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function-Klasse

Konvertiert einen unären Funktionszeiger in eine anwendbare unäre Funktion.

## <a name="syntax"></a>Syntax

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Parameter

*pfunc*<br/>
Die binäre Funktion, die konvertiert werden soll.

*left*<br/>
Das Objekt, auf dem *\*pfunc* aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Die Vorlagenklasse speichert eine Kopie des `pfunc`. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (\* **pfunc**)(_ *Left*).

## <a name="remarks"></a>Hinweise

Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine unäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Für die Verwendung mit einem Adapter, z.B. einen Wert zuzuordnen oder ihn mit einer Negator zu verwenden müssen sie die geschachtelten Typen angegeben werden `argument_type` und `result_type` , die solche Anpassung möglich machen. Die Konvertierung durch `pointer_to_unary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.

## <a name="example"></a>Beispiel

Der Konstruktor von `pointer_to_unary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_unary_function`-Adapterprädikats.

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
