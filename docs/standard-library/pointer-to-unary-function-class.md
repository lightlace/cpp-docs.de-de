---
title: pointer_to_unary_function-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 2b6bf82faa39e22c5af584a9fc3ebf68f5851463
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689143"
---
# <a name="pointer_to_unary_function-class"></a>pointer_to_unary_function-Klasse

Konvertiert einen unären Funktionszeiger in eine anwendbare unäre Funktion. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Parameter

*pFunc* -\
Die binäre Funktion, die konvertiert werden soll.

*Linker* \
Das Objekt, auf dem *\*pfunc* aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

In der-Klassen Vorlage wird eine Kopie von `pfunc` gespeichert. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (\* **pfunc**)(_ *Left*).

## <a name="remarks"></a>Hinweise

Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine unäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Um ihn mit einem Adapter zu verwenden, z. b. das Binden eines Werts an ihn oder dessen Verwendung mit einem Negator, muss er mit den geschachtelte Types `argument_type` und `result_type` bereitgestellt werden, die eine solche Anpassung ermöglichen. Die Konvertierung durch `pointer_to_unary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.

## <a name="example"></a>Beispiel

Der Konstruktor von `pointer_to_unary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_unary_function`-Adapterprädikats.
