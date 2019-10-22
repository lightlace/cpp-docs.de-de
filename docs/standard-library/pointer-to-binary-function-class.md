---
title: pointer_to_binary_function-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 890ebb7d4c2b8fbd51a4460e21efba3e763ead7e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687191"
---
# <a name="pointer_to_binary_function-class"></a>pointer_to_binary_function-Klasse

Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parameter

*pFunc* -\
Die binäre Funktion, die konvertiert werden soll.

*Linker* \
Das linke Objekt, auf dem *\*pfunc* aufgerufen wird.

*Rechte* \
Das rechte Objekt, auf dem *\*pfunc* aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

In der-Klassen Vorlage wird eine Kopie von `pfunc` gespeichert. Er definiert seine Member-Funktion `operator()` als Rückgabe `(* pfunc)(Left, right)`.

## <a name="remarks"></a>Hinweise

Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine binäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Um ihn mit einem Adapter zu verwenden, z. b. das Binden eines Werts an ihn oder dessen Verwendung mit einem Negator, muss er mit den geschachtelte Types `first_argument_type`, `second_argument_type` und `result_type` bereitgestellt werden, die eine solche Anpassung ermöglichen. Die Konvertierung durch `pointer_to_binary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.

## <a name="example"></a>Beispiel

Der Konstruktor von `pointer_to_binary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_binary_function`-Adapterprädikats.
