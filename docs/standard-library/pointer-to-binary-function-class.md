---
title: pointer_to_binary_function-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b632fabe8f596d46a0423d670ff57bb12de93cd
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953455"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function-Klasse

Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion.

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

*Pfunc* binären Funktion, die konvertiert werden.

*linken* das linke Objekt, das  *\*Pfunc* aufgerufen wird.

*richtige* das rechte Objekt, das  *\*Pfunc* aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Die Vorlagenklasse speichert eine Kopie des `pfunc`. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (\* **pfunc**)(_ *Left*, \_ *Right*).

## <a name="remarks"></a>Hinweise

Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine binäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Für die Verwendung mit einem Adapter, z.B. einen Wert zuzuordnen oder ihn mit einer Negator zu verwenden müssen sie die geschachtelten Typen angegeben werden `first_argument_type`, `second_argument_type`, und `result_type` , die solche Anpassung möglich machen. Die Konvertierung durch `pointer_to_binary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.

## <a name="example"></a>Beispiel

Der Konstruktor von `pointer_to_binary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_binary_function`-Adapterprädikats.

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
